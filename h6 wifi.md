# h6 kotitehtävät
### Linkki wWifiChallenge Labiin. https://lab.wifichallenge.com/challenges

## a) Tutustu wifi challenge lab 2.1 harjoitus ympäristöön ja käytä tarvittaessa hyväksesi jo olemassa olevia ohjeita.
Tämä alkoi hyvin kunnes WCL:in virtuaalikoneessa ei ollutkaan tarvittavia ohjelmia tehdä tehtäviä. Ehdin itse opetelle ja tehdä RECON osuuden. Mutta OPN osuudessa tarvittavaa wpa_suplicant ohjelmaa ei löytynyt koneesta ja sitä en osannut siihen kuvaan asentaa.
Loput harjoituksista seurasin walktrough:n kautta (https://r4ulcl.com/posts/walkthrough-wifichallenge-lab-2.0/#recon). Ja jos espanian kieli taipuu niin voi myös seurata Pez Ejecutivon sarjaa https://r4ulcl.com/posts/walkthrough-wifichallenge-lab-2.0/#05-what-is-the-flag-in-the-hidden-ap-router-behind-default-credentials
ja https://www.youtube.com/watch?v=K42uVvTJK5o kannattaa seuralailla.

<img width="1443" height="656" alt="image" src="https://github.com/user-attachments/assets/6807626e-aa67-499c-81a2-b9e7e1aa5db2" />

<img width="1537" height="567" alt="Näyttökuva 2025-11-16 232710" src="https://github.com/user-attachments/assets/bb3f92a7-ef63-47c9-9342-bc790cbeb38a" />

## b) Kirjoita raportti siitä mitä opit ja mitkä asia yllättivät sinut kun tutustuit harjoitukseen.
Harjoituksen aikana opin, että WLANin turvallisuus riippuu suurelta osin verkon asetuksista ja käytetyistä salausmenetelmistä. Opin, että piilotettu SSID ei tarjoa merkittävää lisäsuojaa, sillä verkon voi paljastaa nopeasti oikeilla työkaluilla. Lisäksi opin, että oletusasetusten käyttäminen tekee verkosta helposti saavutettavan hyökkääjälle, ja että hallintapaneeliin pääsy oletustunnuksilla on todellinen riski.

Harjoitus osoitti myös, että langattoman liikenteen seuraaminen on teknisesti helppoa, jos suojaus puuttuu. Työkalut kuten airodump-ng ja mdk4 mahdollistavat sekä passiivisen että aktiivisen tiedonkeruun, mikä havainnollisti, että hyökkäyksen toteuttamiseen ei välttämättä tarvita erityistä teknistä osaamista.

Harjoituksessa yllätti erityisesti se, kuinka nopeasti piilotettu verkko voidaan selvittää ja kuinka helposti oletustunnuksilla pääsee käsiksi reitittimen hallintaan. Lisäksi oli yllättävää huomata, että verkon liikennettä voi seurata tehokkaasti yksinkertaisin välinein, mikä korostaa salauksen ja VPN:n merkitystä. Myös työkalujen helppokäyttöisyys ja monipuolisuus yllättivät, sillä niiden avulla voi kerätä paljon tietoa verkosta lyhyessä ajassa.

## c) Miten suhtautumisesi WLanin turvallisuuteen muuttui sen jälkeen kun teit harjoitukset?
Harjoitusten jälkeen suhtautumiseni WLAN-turvallisuuteen muuttui selvästi kriittisemmäksi ja tietoisemmaksi. Yksi merkittävimmistä oivalluksista oli se, kuinka yleistä on, että suurta osaa reitittimistä käytetään edelleen täysin oletusasetuksilla. Labraympäristössä käytetyt tunnukset ja asetukset löytyy valitettavan usein myös oikeista verkoista. Tämä korosti, sitä että suuri riski on avoin tai huonosti konfiguroitu reititin, sillä se mahdollistaa esteettömän pääsyn verkkoon.

Toinen keskeinen oppi liittyi WLAN-liikenteen kuunteluun. Harjoituksissa selvisi, että kuka tahansa voi kuunnella salaamatonta liikennettä. Tämä sai ymmärtämään, kuinka helposti esimerkiksi kirjautumistietoja tai muuta arkaluonteista liikennettä voisi joutua vääriin käsiin.

Lisäksi harjoitukset osoittivat, kuinka paljon hyökkääjä voi saada aikaan yhdistämällä muutamia työkaluja. Esimerkiksi airodump-ng ja mdk4 mahdollistavat sekä passiivisen että aktiivisen tiedonkeruun yllättävän helposti, jopa yksittäiselle käyttäjälle ilman erityisen syvää teknistä osaamista. Tämä korostaa tarvetta oikeille suojausmenetelmille.

Yksi harjoituksen yllättävimmistä havainnoista oli piilotetun SSID:n paljastaminen. Harjoituksissa piilotettu SSID saatiin selville vain muutamassa minuutissa, mikä osoittaa, ettei menetelmää voi pitää todellisena turvakeinona.

Kokonaisuudessaan harjoitukset osoittivat selkeästi, että WLAN ei ole turvallinen oletuksena. Turvallisuus täytyy rakentaa itse käyttämällä esimerkiksi WPA2- tai WPA3-suojausta, vaihtamalla oletussalasanat ja konfiguroimalla verkko kunnolla. Lisäksi on tärkeää käyttää VPN:ää julkisissa verkoissa ja ymmärtää, kuinka helposti liikennettä voidaan seurata ilman salausta.
