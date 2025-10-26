# h1 Sniff
## x) Lue ja tiivistä. (Tässä x-alakohdassa ei tarvitse tehdä testejä tietokoneella, vain lukeminen tai kuunteleminen ja tiivistelmä riittää. Tiivistämiseen riittää muutama ranskalainen viiva.)
 - Karvinen 2025: Wireshark - Getting Started
 - Karvinen 2025: Network Interface Names on Linux
## b) Ei voi kalastaa. Osoita, että pystyt katkaisemaan ja palauttamaan virtuaalikoneen Internet-yhteyden.

<img width="1174" height="481" alt="Näyttökuva 2025-10-26 142026" src="https://github.com/user-attachments/assets/fd9f3205-a1b5-419b-895b-e9960f07f96d" />

<img width="940" height="466" alt="Näyttökuva 2025-10-26 142128" src="https://github.com/user-attachments/assets/dfa68525-b0c8-4549-983c-d692997cecd0" />

## c) Wireshark. Asenna Wireshark. Sieppaa liikennettä Wiresharkilla. (Vain omaa liikennettäsi. Voit käyttää tähän esimerkiksi virtuaalikonetta).
Kalilla tämä on valmiiksi asennettuna, mutta jos sitä ei ole niin komennolla sudo apt install wireshark -y saa sen ladattua.

## d) Oikeesti TCP/IP. Osoita TCP/IP-mallin neljä kerrosta yhdestä siepatusta paketista. Voit selityksen tueksi laatikoida ne ruutukaappauksesta. (Voit käyttää vastauksesi osana ruutukaappaustasi h0-tehtävästä, mutta tässä tehtävässä tarvitaan myös sanallinen selitys.)
Tehty tässä: https://github.com/MikoLiukk/Verkkoon-tunkeutuminen-ja-tiedustelu/blob/main/H0%20Hei%20maailma.md

## e) Mitäs tuli surffattua? Avaa surfing-secure.pcap. Tutustu siihen pintapuolisesti ja kuvaile, millainen kaappaus on kyseessä. Tässä siis vain lyhyesti ja yleisellä tasolla. Voit esimerkiksi vilkaista, montako konetta näkyy, mitä protokollia pistää silmään. Määrästä voit arvioida esimerkiksi pakettien lukumäärää, kaappauksen kokoa ja kestoa.

## g) Minkä merkkinen verkkokortti käyttäjällä on? surfing-secure.pcap

## h) Millä weppipalvelimella käyttäjä on surffaillut? surfing-secure.pcap
Huonoja uutisia: yhteys on suojattu TLS-salauksella.
