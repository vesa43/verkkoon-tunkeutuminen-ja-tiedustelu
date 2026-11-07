## tehtävä x)



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

## tehtävä e)

Ultimate Radio Hackerin sai asennettua asentamalla ensin pipx paketin komennolla `sudo apt install pipx` ja URH:n komennolla `pipx install urh`

<img width="718" height="88" alt="image" src="https://github.com/user-attachments/assets/61ed9c27-b795-4d35-a785-a8d20129695b" />

### f)

Tiedoston nimestä näkee jo, että kyseessä on näyte taajuudella `433.912MHz` ja Sample raten asettaa `2.0M` niin ohjelmassa näkyy näytteen pituutena `2.75s`
