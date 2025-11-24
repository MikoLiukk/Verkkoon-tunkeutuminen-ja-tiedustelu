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
