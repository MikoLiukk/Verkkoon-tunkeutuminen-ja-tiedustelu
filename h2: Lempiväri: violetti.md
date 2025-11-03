# h2 Tehtävänannot
## x) Lue ja vastaa lyhyesti kysymyksiin. Tässä alakohdassa x ei tällä kertaa tarvitse lukea artikkeleita kokonaan, ei tarvitse tiivistää niitä, eikä tehdä testejä koneella.
- Selitä tuskan pyramidin idea 1-2 virkkeellä. Bianco 2013: Pyramid of Pain. (Katso eritoten pyramidin kuvaa.) https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html
   - Konsepti, joka kuvaa kuinka vaikeaa hyökkäjälle on sopeutua kun puolustaja tunnistaa ja estää eri tasoisia hyökkäysindikaattoreita. Mitä korkeammalle pyramidissa noustaan, sitä enemmän “kipua” hyökkääjälle aiheutetaan ja sitä kestävämpi puolustus saavutetaan

- Selitä timanttimallin (Diamond Model) idea 1-2 virkkeellä. Tekijä esittelee sen aika juhlallisesti, voit myös etsiä yksinkertaisempia artikkeleita hakukoneella tai kelata suoraan timantin kuvaan. Caltagirone et al 2013: Diamond Model. https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf
  - Timanttimalli kuvaa hyökkäystä neljän peruselementin ja niiden välisten suhteiden kautta: Adversary (hyökkääjä), Capability (kyvykkyys), Infrastructure (infrastruktuuri) ja Victim (kohde).

## a) Apache log. Asenna Apache-weppipalvelin paikalliselle virtuaalikoneellesi. Surffaa palvelimellesi salaamattomalla HTTP-yhteydellä, http://localhost . Etsi omaa sivulataustasi vastaava lokirivi. Analysoi yksi tällainen lokirivi, eli selitä sen kaikki kohdat. (Jos Apache ei ole kovin tuttu, voit tätä tehtävää varten vain asentaa sen ja testata oletusweppisivulla. Eli ei tarvitse tehdä omia kotisvuja tms.)

<img width="933" height="542" alt="Näyttökuva 2025-11-03 004351" src="https://github.com/user-attachments/assets/e84fdb03-bfe5-4440-93cd-6bddb1a2f355" />

<img width="928" height="78" alt="Näyttökuva 2025-11-03 004434" src="https://github.com/user-attachments/assets/e7790c28-0c87-4c56-9215-5d46546f7944" />
127.0.01 - Asiakkaan IP-osoite (localhost) - on käyttäjätunnus, sitten meillä on päivämäärä ja aika, sitten http GET-pyyntö, pyydetty resurssi ja protokolla, palautukoodi 200, vasteen koko tavuina ja käyttäjän User-Agent.

## b) Nmapped. Porttiskannaa oma weppipalvelimesi käyttäen localhost-osoitetta ja 'nmap -A' päällä. Selitä tulokset. (Pelkkä http-portti 80/tcp riittää)

<img width="842" height="331" alt="Näyttökuva 2025-11-02 232552" src="https://github.com/user-attachments/assets/28fe708e-1afe-4e37-a77e-f14fca73ca38" />

Protti skannauksessa löytyi, että portti 80 on ainoa auki oleva portti.

## c) Skriptit. Mitkä skriptit olivat automaattisesti päällä, kun käytit "-A" parametria? (Näkyy avoimien porttinumeroiden alta, http-blah, http-blöh...).

<img width="476" height="852" alt="Näyttökuva 2025-11-03 004829" src="https://github.com/user-attachments/assets/95bd8a9f-94cd-4cf7-9ed2-3f41bfc431c1" />

## d) Jäljet lokissa. Etsi weppipalvelimen lokeista jäljet porttiskannauksesta (NSE eli Nmap Scripting Engine -skripteistä skannauksessa). Löydätkö sanan "nmap" isolla tai pienellä? Selitä osumat. Millaisilla hauilla tai säännöillä voisit 
tunnistaa porttiskannauksen jostain muusta lokista, jos se on niin laaja, että et pysty lukemaan itse kaikkia rivejä?

<img width="932" height="805" alt="Näyttökuva 2025-11-03 004958" src="https://github.com/user-attachments/assets/3152f8f8-378d-48e3-ac56-6d51199a6235" />


## e) Wire sharking. Sieppaa verkkoliikenne porttiskannatessa Wiresharkilla. Huomaa, että localhost käyttää "Loopback adapter" eli "lo". Tallenna pcap. Etsi kohdat, joilla on sana "nmap" ja kommentoi niitä. Jokaisen paketin jokaista kohtaa ei tarvitse analysoida, yleisempi tarkastelu riittää.
Paketit on loopbackeja, joka ei yllättänyt. User-Agent myös löytyy. Pakettien sisältämä NMAP on aika selvä todiste porttiskannauksesta.
<img width="956" height="821" alt="Näyttökuva 2025-11-03 005458" src="https://github.com/user-attachments/assets/efbb4db8-2d05-40c3-a29e-3595e45cd93d" />

## f) Net grep. Sieppaa verkkoliikenne 'ngrep' komennolla ja näytä kohdat, joissa on sana "nmap".

<img width="920" height="866" alt="Näyttökuva 2025-11-03 005659" src="https://github.com/user-attachments/assets/03018b46-6dc9-42bd-afb6-27fef263e4be" />

## g) Agentti. Vaihda nmap:n user-agent niin, että se näyttää tavalliselta weppiselaimelta.

<img width="1902" height="416" alt="Näyttökuva 2025-11-03 005908" src="https://github.com/user-attachments/assets/698a585b-c0e4-4a38-a8c8-87d9f96fad8d" />

## h) Pienemmät jäljet. Porttiskannaa weppipalvelimesi uudelleen localhost-osoitteella. Tarkastele sekä Apachen lokia että siepattua verkkoliikennettä. Mikä on muuttunut, kun vaihdoit user-agent:n? Löytyykö lokista edelleen tekstijono "nmap"?
Ei löydy, kun UA:n muuttaa
<img width="1902" height="416" alt="Näyttökuva 2025-11-03 005908" src="https://github.com/user-attachments/assets/7a668852-4423-42ba-b137-54e3671dfbfc" />

## i) Hieman vaikeampi: LoWeR ChEcK. Poista skritiskannauksesta viimeinenkin "nmap" -teksti. Etsi löytämääsi tekstiä /usr/share/nmap -hakemistosta ja korvaa se toisella. Tee porttiskannaus ja tarkista, että "nmap" ei näy isolla eikä pienellä kirjoitettuna Apachen lokissa eikä siepatussa verkkoliikenteessä. (Tässä tehtävässä voit muokata suoraan lua-skriptejä /usr/share/nmap alta, 'sudoedit'. Muokatun version paketoiminen siis rajataan ulos tehtävästä.)

<img width="1902" height="416" alt="Näyttökuva 2025-11-03 005908" src="https://github.com/user-attachments/assets/eb117b10-b541-4281-a433-b3ce556b7d95" />
