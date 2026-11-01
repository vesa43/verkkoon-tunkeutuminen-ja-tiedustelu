## tehtävä x)

Tiivistelmä karvinen 2025: Wireshark - Getting Started (https://terokarvinen.com/wireshark-getting-started/)

- Sivulla kerrotaan kuinka wireshark voidaan asentaa linuxille, esimerkissä on käytössä debian.
- Wireshark asennus tapahtuu komennolla `sudo apt install wireshark`
- Komennolla `sudo adduser käyttäjänimi wireshark` voidaan lisätä käyttäjä wireshark ryhmään, jotta jos wiresharkkia halutaan käyttää ilman sudoa.
- Wiresharkista löytyy paljon hyviä display filttereitä, joilla voidaan suodattaa juuri niitä paketteja joita halutaan nähdä.

Tiivistelmä karvinen 2025: Network Interface Names on Linux (https://terokarvinen.com/network-interface-linux/)

- Sivulla kuvataan eri network interface nimiä mitä ne tarkoittaa.
- en = ethernet
- wl = Wlan
- lo = Loopback adapter
- Omat interfacet löytää helposti komennoilla `ip a` ja `ip route`


## tehtävä a)

asensin debianin jo etukäteen, ja asennuksessa ei ollut mitään ongelmaa.

## tehtävä b)

Nettiyhteyden katkaisemiseen on monia eri tapoja mutta valitsin nyt simppelin tavan, jolla saa netin katkaistua yhdellä napin painalluksella visuaalisen käyttöliittymän kautta.
Kuvassa alla näkyy valikko jonka saa auki klikkaamalla oikeasta yläkulmasta (punainen nuoli) ja sen jälkeen netin saa katki painamalla netti yhteyden kuvaketta (vihreä nuoli)

<img width="456" height="244" alt="image" src="https://github.com/user-attachments/assets/db622f48-8923-4aaa-9a39-4fccb62b122c" />

Kun netti yhteys on laitettu katki, voidaan kokeilla tätä käytännössä esimerkiksi pingaamalla terminalissa google osoitetta "8.8.8.8", jolloin saadaan ilmoitus "Network is unreachable".

<img width="566" height="261" alt="image" src="https://github.com/user-attachments/assets/d6a16784-938b-4d4a-b088-24d9e02fe098" />

Netti yhteyden saa helposti takaisin kun painaa täysin samaa näppäintä uudelleen. Tämän jälkeen ping komento toimii ja paketit lähtevät ja saapuvat takaisin normaalisti.

<img width="623" height="321" alt="image" src="https://github.com/user-attachments/assets/890c2497-c252-4851-a696-164843d33651" />



## tehtävä c)

Wireshark asennus tapahtui käyttämällä komentoa `sudo apt install wireshark` <img width="760" height="211" alt="image" src="https://github.com/user-attachments/assets/2452b63a-1ca0-4cf3-bc6e-d1c7f1cb115a" />

avasin wiresharkin ja käyttämällä komentoa sudo wireshark, sieppasin lyhyen pätkän liikennettä. 

<img width="974" height="410" alt="image" src="https://github.com/user-attachments/assets/b4bdd2e7-2829-4f17-b4ac-910ace2ad357" />



## tehtävä d)

<img width="824" height="280" alt="image" src="https://github.com/user-attachments/assets/4b181942-54da-49d8-98d2-8fe85e88b2b4" />

Otin listalta yhden udp paketin katseluun ja siitä nähdään kerrokset seuraavilla väreillä merkattuna
- punainen: Link layer
- vihreä: internet layer
- sininen: transport layer
- keltainen: application layer


## tehtävä e)

Tarkastelemalla paketteja, heti alusta pistää silmään ensimmäiset paketit, jossa on selvästi dns kysely ipv4 (A) osoitteelle sekä ipv6 (AAAA) osoitteelle. tämän jälkeen siirrytään QUIC-protokollaan 

Loppupäästä voidaan suoraan katsoa, että paketteja oli yhteensä 283, ja viimeisen paketin aikaleima oli noin 7,5. Tästä voidaan päätellä, että sieppaus oli ainakin 7,5 sekunnin ajalta.

<img width="203" height="105" alt="image" src="https://github.com/user-attachments/assets/e3a1b3f8-41b6-4923-a86f-0d1c84143cb5" />

Jos taas katsotaan statistics -> endpoints voidaan nähdä ainakin 7 eri ip osoitetta.

<img width="587" height="206" alt="image" src="https://github.com/user-attachments/assets/bf80b807-0608-43b7-a584-5c8b4f99c313" />

Koko kaappaus alun nimi kyselyjen kanssa ja lopun RST tägin sisältävät paketit, antavat sellaista kuvaa että sieppaus on aloitettu jonka jälkeen selain on avattu ja sieltä esim. sivu kuten terokarvinen.com, ja lopulta selain on suljettu ja sieppaus päättyy sen jälkeen. 

## tehtävä g)

Verkkokortin valmistajan voisi yleisesti tarkastaa mac adressia käyttämällä, mutta tässä tapauksessa tästä osoitteesta selviää, että käytössä on locally administered address (LAA). tällä osoitteella ei siis voi löytää verkkokortin merkkiä. Kyseessä voisi esimerkiksi olla virtuualikone, jossa saattaisi olla juuri käytössä tällainen LAA, mutta sitä ei pysty sanomaan varmaksi.

<img width="802" height="238" alt="image" src="https://github.com/user-attachments/assets/ea2861b7-5c45-4f91-a807-b38d865f4af2" />


## tehtävä h)

dns protokollan paketteja ja tls protokollan infon sni= arvoa katsomalla voidaan ainakin löytää seuraavia osoitteita: google.com, terokarvinen.com, gc.zgo.at, goatcounter.netlify.com ja terokarvinen.goatcounter.com

## tehtävä i)

<img width="1324" height="433" alt="image" src="https://github.com/user-attachments/assets/1c66113f-7be3-4ec2-be45-0e63d069eec8" />

Kuvaan on otettu lyhyt pätkä siepattua liikennettä kotinetistä.

heti ensimmäisenä näyttää olevan hauska kyllä mielen wwg888 mallinen pesukone joka kertoo näköjään olemassa olostaan muille verkon laitteille.
toinen paketti on tpLinkin mesh verkon jotain omaa viestittelyä.
paketit 3-6 on tullut, koska avasin tätä varten twitch.com sivuston ja tässä oma kone näyttäisi kyselevän dnssältä ositetta ja tähän tulee heti perään vastaus takaisin.
Paketit 7-17 taas liittyvät siihen kuinka tcp protokollalla aloitetaan kättely ja client lähettää aloituspyynnön twitchille, ja sieltä tulee myöntävä vastaus ja client yhteyden.
paketin 10 kohdalla siirrytään tls v1.3 protokollaan jolla lähetetään niin sanottu client hello johon palvelin vastaa ja tämän jälkeen kaikki liikenne salataan.
