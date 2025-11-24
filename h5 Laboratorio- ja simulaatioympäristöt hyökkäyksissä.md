# h5
## a) Tutustu seuraavaan työkaluun
https://github.com/kgretzky/evilginx2
Vastaa seuraaviin kysymyksiin
### Asensitko työkalun, jos asensit niin kirjoita miten sen teit.
Asensin työkalun seuraavasti:
git clone https://github.com/kgretzky/evilginx2.git, tällä asensin suoraan githubista sorsat virtuaalikoneelle
cd evilginx2
make
sudo make install

vaihtoehtoisesti ilmeisesti toimii myös ihan
sudo apt install evilginx2

### Mitä teit työkalun kanssa?
Testasin työkalulla tehdä kalastelusivun, jolla saisin kaapattua käyttäjän käyttäjänimen ja salasanan. Työkalu on siitä vaarallinen, että sillä voi välttää 2FA.

### Onnistuitko huijaamaan liikennettä
Loppujen lopuksi yritykseni kaatui, koska en saanut firefoxia hyväksymään serttiä monen tunnin yrityksen jälkeen, mutta ymmärrän sen, että kuinka päätteeseen tieto tulisi, jos joku laittaisi tiedonsa siihen.

<img width="909" height="841" alt="Näyttökuva 2025-11-23 234829" src="https://github.com/user-attachments/assets/532b0bb7-3bee-407b-bfcb-8d35569c5c74" />

Käytin apunani opiskelija toverin hyvin tehtyjä ohjeita. https://github.com/p-lemonish/course-network-attacks-and-reconnaissance/blob/main/5/h5.md 

config domain evilginx-text.com
config ipv4 127.0.0.1
phishlets hostname example jokinsivutahan.evilginx-text-com
phishlets enable example
lures create example
lures get-url "0-100"

## b) Sinulla on käytössäsi mininet ympäristö. Luo ympäristö, jossa voit tehdä TCP SYN-Flood hyökkäyksen.
### Kirjoita miten loit mininet ympäristön ja miten toteutit hyökkäyksen.
TCP SYN-flood, minulle ehkä tutummin (D)dos, jos on joskus pelannut verkoss moninpelejä ja jollekkin tulee liian paha mieli, pääsee kokemaan tämän vaikutukset.

Valmiiksi annettu kuva päälle ja luodaan mininet ja verkko-ohjain tunnilla saaduilla komennoilla:
´´´´
ryu-manager ryu.app.simple_switch_13
sudo mn --topo single,3 --mac --switch ovsk --controller remote
pingall
´´´´
Sitten vain nodet auki taikakeksien avulla
xterm h1-3

H1 shellistä hyökkäys eteenpäin 
sudo hping3 -S --flood -p 80 10.0.0.2
Tässä huomiona, että hping3 luo TCP paketit "käsin" ja -S on SYN-lippu, eli luo TCP-yhteyden avauspyyntöjä, kun --flood on se mikä ylikuormittaa vastaanottajan päässä laitteet, eli lähettää paketit mahdollisimman nopeasti, ilman rajoituksia. Tästä tulee TCP SYN-flood.

Tässä kohtaa wireshark huusi tuhatta ja punaista, mutta tuloksetta, paketteja tuli niin paljon ja useasti, että läppärini suorituskykyloppui kesken, mutta henkilökohtaisen kokemuksen perusteella, voin sanoa että tuli käytettyä hyökkäystä itseeni onnistuneesti.

<img width="699" height="568" alt="Näyttökuva 2025-11-24 025128" src="https://github.com/user-attachments/assets/374c67a3-d7b9-47d5-9490-faf8ccf3dcc6" />

### Lähteet
https://www.firewall.cx/tools-tips-reviews/network-protocol-analyzers/performing-tcp-syn-flood-attack-and-detecting-it-with-wireshark.html#how-to-perform-syn-flood-attack
https://github.com/p-lemonish/course-network-attacks-and-reconnaissance/blob/main/5/h5.md
https://help.evilginx.com/community/getting-started/quickstart
https://help.evilginx.com/community/getting-started/deployment/local
https://www.youtube.com/watch?v=fVGZbMGH558


