# h7
### x) Lue ja tiivistä. (Tässä x-alakohdassa ei tarvitse tehdä testejä tietokoneella, vain lukeminen tai kuunteleminen ja tiivistelmä riittää. Tiivistämiseen riittää muutama ranskalainen viiva.)
Hubacek 2019: Universal Radio Hacker SDR Tutorial on 433 MHz radio plugs (Video, alkaen 3:19 ja päättyen 7:40. Yhteensä noin 4 min.)
- Videossa Martin käy läpi kuin URH käytetään.
  
### Cornelius 2022: Decode 433.92 MHz weather station data
- SDR tallenteen dekoodaus
- OOK/PPM-modulaatio
- Lopputuloksena valmis konffaus rtl_433

## a) WebSDR. Etäkäytä WebSDR-ohjelmaradiota, joka on kaukana sinusta ja kuuntele radioliikennettä. Radioliikenne tulee siepata niin, että radiovastaanotin on joko eri maassa tai vähintään 400 km paikasta, jossa teet tätä tehtävää. Käytä esimerkkinä julkista, suurelle yleisölle tarkoitettua viestiä, esimerkiksi yleisradiolähetystä. Kerro löytämäsi taajuus, aallonpituus ja modulaatio. Kuvaile askeleet ja ota ruutukaappaus. (Tehtävässä ei saa ilmaista sellaisen viestin sisältöä tai olemassaoloa, joka ei ole tarkoitettu julkiseksi. Voit sen sijaan kuvailla, miten sait julkisen radiolähetyksen kuulumaan kaiuttimistasi. Julkisten, esimerkiksi yleisradiolähetysten sisältöä saa tietysti kuvailla.)
Valitsin Californiassa sijaitsevan Santa Claritan sijainnin. Kuuntelin 829.50 kHz lähetystä kello 20:30 7.12.2025.

<img width="1610" height="691" alt="Näyttökuva 2025-12-07 202522" src="https://github.com/user-attachments/assets/80b3f3e1-5d7e-4f8a-b504-32a7926b9d5b" />

Lähetyksessä kuunneltiin amerikkailasen jalkapallon ottelua.

## b) rtl_433. Asenna rtl_433 automaattista analyysia varten. Kokeile, että voit ajaa sitä. './rtl_433' vastaa "rtl_433 version 25.02 branch..
Asennus onnistui ihan sudo apt-get rtl-443 komennolla.

<img width="634" height="74" alt="Näyttökuva 2025-12-07 203503" src="https://github.com/user-attachments/assets/e6ea4622-a0ce-4553-add6-e4bfb77b3015" />


## c) Automaattinen analyysi. Mitä tässä näytteessä tapahtuu? Mitä tunnisteita (id yms) löydät? Converted_433.92M_2000k.cs8. Analysoi näyte 'rtl_433' ohjelmalla.

<img width="955" height="835" alt="Näyttökuva 2025-12-07 204025" src="https://github.com/user-attachments/assets/0f4282cd-cb55-419d-86cb-29d50eecfb05" />

<img width="954" height="836" alt="Näyttökuva 2025-12-07 204146" src="https://github.com/user-attachments/assets/b9d2ad23-e965-46c0-a70d-3401b6a04a6a" />

Tilanteessa todennäköisesti painetaan samanlaisen vekottimen nappia kuin tunnilla 2.12, laite ilmeisesti laittaa valoja päälle ja pois radioaalloilla.

## d) Too compex 16? Olet nauhoittanut näytteen 'urh' -ohjelmalla .complex16s-muodossa. Muunna näyte rtl_433-yhteensopivaan muotoon ja analysoi se. Näyte Recorded-HackRF-20250411_183354-433_92MHz-2MSps-2MHz.complex16s
Tässä minulla oli latauksen kanssa ongelmia. Tiedoston koko oli niin pieni ja sisälsi pelkkää 0000 binääriä, niin en nähnyt tarpeelliseksi enään kääntää tiedostoa oikeaan muotoon.
Yritetty eri selaimia.

<img width="890" height="815" alt="Näyttökuva 2025-12-07 212124" src="https://github.com/user-attachments/assets/ecd3620b-f387-44cc-b6db-0718a8a375c8" />

## e) Ultimate. Asenna URH, the Ultimate Radio Hacker.
Teron antamat ohjeet eivät toimineet minun ympäristössä, joten jouduin asentaa URH:n dockeriin.
Ensin git clone https://github.com/jopohl/urh.git

En saanut asennettua pipx:ässä URH ja kun koitti python3 -m pip install --upgrade pip setuptools wheel tuli vastaukseksi This environment is externally managed, ilmeisesti Kali on ongelma.
Käännyin ChatGPT puolelle, joka ohjeisti minut pyörittämään URH Dockerin ouolella.
sudo apt install docker.io docker-compose
sudo systemctl enable --now docker
sudo usermod -aG docker $USER
Kirjaudu ulos ja takaisin sisään.
xhost +local:docker
mkdir -p ~/urh-data
docker run --rm -it \
    -e DISPLAY=$DISPLAY \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -v ~/urh-data:/root/urh-data \
    jopohl/urh:latest

<img width="573" height="227" alt="Näyttökuva 2025-12-08 013014" src="https://github.com/user-attachments/assets/bfb63919-dc00-4d3b-88f7-3a1147eb1549" />

## Tarkastele näytettä 1-on-on-on-HackRF-20250412_113805-433_912MHz-2MSps-2MHz.complex16s. Siinä Nexan pistorasian kaukosäätimen valon 1 ON -nappia on painettu kolmesti. Käytä Ultimate Radio Hacker 'urh' -ohjelmaa.
## f) Yleiskuva. Kuvaile näytettä yleisesti: kuinka pitkä, millä taajuudella, milloin nauhoitettu? Miltä näyte silmämääräisesti näyttää?
Oletin tiedostonimestä, minkälainen tiedosto on kyseessä.
Taajuus 433,912MHz, Nauhoitettu 4.12.2025 kello 11:38:05 ja URH:sta näkee, että näyte on noin 5,5 sekunttia pitkä

<img width="1913" height="559" alt="Näyttökuva 2025-12-08 013612" src="https://github.com/user-attachments/assets/8ce4cf40-c24d-44fa-ba93-4419b8773e7c" />

## g) Bittistä. Demoduloi signaali niin, että saat raakabittejä. Mikä on oikea modulaatio? Miten pitkä yksi raakabitti on ajassa? Kuvaile tätä aikaa vertaamalla sitä johonkin. (Monissa singaaleissa on line encoding, eli lopullisia bittejä varten näitä "raakabittejä" on vielä käsiteltävä)
Kyyseessä on OOK-modulaatio On-off Keying, yksi pulssi on noin 350ms
<img width="1910" height="537" alt="Näyttökuva 2025-12-08 014200" src="https://github.com/user-attachments/assets/1dd2e027-a3d6-4644-89b1-ee686180d849" />
