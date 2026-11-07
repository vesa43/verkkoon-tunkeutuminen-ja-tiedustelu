## tehtävä x)

Hubacek 2019: Universal Radio Hacker SDR Tutorial on 433 MHz radio plugs: (https://youtu.be/sbqMqb6FVMY?t=199)
- Taajuus voidaan etsiä URH:n spectrum analyzeri työkalulla.
- Signaali saadaan nauhoitettua Record signal osiosta.
- Videossa modulaatioksi valittiin ASK, jolla työkalu osaa itse määrittää muut parametrit.
- Signal view: demodulated tilalla voidaan nähdä bitit selkeästi kuvaajasta

Cornelius 2022: (https://www.onetransistor.eu/2022/01/decode-433mhz-ask-signal.html)
- Lämpötila anturin signaali saatiin tallennettua käyttämällä rtl-433 softaa.
- rtl_433 osasi suoraan purkaa signaalin ja antaa oikeita mittaus tuloksia ilman kosteudelle ja lämpötilalle.
- URH:n avulla signaalista saatiin mitattua aika jonka välein laite lähettää dataa (56,75s)
- Jotta data saatiin muutettua luettaviksi biteiksi, piti ensin luoda oma decode sääntö, jonka avulla signaali saadaan haluttuun muotoon

## tehtävä b)

Aloitin tehtävän tarkastamalla että paketit on päivitetty komennolla `sudo apt update`. Tämän jälkeen asensin rtl paketin komennolla `sudo apt install rtl-433`. Kaikki näytti toimivan ja rtl on nyt asennettu onnistuneesti.

<img width="646" height="73" alt="image" src="https://github.com/user-attachments/assets/bbb2f932-754c-4258-96a3-265421bbc744" />


## tehtävä c)

Tehtävän näytetiedoston sai avattua komennolla `rtl_433 Converted_433.92M_2000k.cs8`. Tiedostosta voi nähdä aina 3 signaalia samalla aikaleimalla kerrallaan, joissa kaikissa on saman laitteen id `8785315`. Oleellinen tieto löytyy oikeastaan aina kolmikon ekasta kohdasta, jossa laitteen malli on nimellä `KlikAanKlikUit-Switch`. Tästä voidaan nähdä command kohdassa off, eli luultavasti on painettu jostain kaukosäätimestä sammutusnappia. Sama on toistettu näytteessä 4 kertaa peräkkäin. Alla vielä kuva tästä kolmikosta ja nuolilla merkitty mainitut asiat.

<img width="937" height="343" alt="image" src="https://github.com/user-attachments/assets/26630174-6fcf-41a2-9a23-a676fefe1925" />


## tehtävä d)

Tehtävän tiedoston sain ajettua Kopioimalla tiedoston samalla nimellä mutta vaihtamalla päätteen muotoon `.cs8`. Käytin tähän ihan perus `cp` komentoa.

<img width="764" height="57" alt="image" src="https://github.com/user-attachments/assets/3da3e2d0-eff4-4d2a-ac61-d5e967c34810" />

Tämän jälkeen tiedoston sai ajettua komennolla `rtl_433 tiedoston nimi päättellä .cs8`.

<img width="760" height="367" alt="image" src="https://github.com/user-attachments/assets/cd3f82b4-2f0a-4edf-a294-ebcb092d804e" />

Näyte näyttää olevan tismalleen sama kuten edellisessä joten analyysi edellisessä tehtävässä.

## tehtävä e)

Ultimate Radio Hackerin sai asennettua asentamalla ensin pipx paketin komennolla `sudo apt install pipx` ja URH:n komennolla `pipx install urh`

<img width="718" height="88" alt="image" src="https://github.com/user-attachments/assets/61ed9c27-b795-4d35-a785-a8d20129695b" />

### f)

Tiedoston nimestä näkee jo, että kyseessä on näyte taajuudella `433.912MHz` ja jos sample raten asettaa `2.0M` niin ohjelmassa näkyy näytteen pituutena `2.75s`. En saanut selville milloin näyte on otettu.

### g)

Kun näytteen antoi URH ja painoi painiketta "Autodetect parameters, pystyttiin löytämään, että yksi bitti on noin 260 mikrosekuntia tai noin 520 samplea.

<img width="730" height="432" alt="image" src="https://github.com/user-attachments/assets/a5ddd1d8-1495-47a2-a385-2e13128bb1a5" />

Vertauksena 260mikrosekuntia on sama kuin 0,26millisekuntia, eli vielä 4 kertaa pienempi kuin vaikka joissain online peleissä, joissa serveri sijaitsee hyvin lähellä ja ping voi olla (1ms).
Huippunopealla peli 720hz pelinäytölläkin menee noin 1,39ms päivittää uusi kuva ruudulle.

Lähteet:
Karvinen, T. 2026. Verkkoon tunkeutuminen ja tiedustelu. Verkkosivu. Luettavissa: https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/. Luettu: 8.11.2026

Hubacek 2019. Universal Radio Hacker SDR Tutorial on 433 MHz radio plugs. Video. Katsottavissa: (https://youtu.be/sbqMqb6FVMY)

Cornelius 2022. Decode 433.92 MHz weather station data. Verkkosivu. Luettavissa: https://www.onetransistor.eu/2022/01/decode-433mhz-ask-signal.html. Luettu: 8.11.2026
