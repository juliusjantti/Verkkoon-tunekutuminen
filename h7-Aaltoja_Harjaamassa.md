# TEHTÄVÄT

x) Lue ja tiivistä. (Tässä x-alakohdassa ei tarvitse tehdä testejä tietokoneella, vain lukeminen tai kuunteleminen ja tiivistelmä riittää. Tiivistämiseen riittää muutama ranskalainen viiva.)

[Hubacek 2019: Universal Radio Hacker SDR Tutorial on 433 MHz radio plugs (Video, alkaen 3:19 ja päättyen 7:40. Yhteensä noin 4 min.)](https://www.youtube.com/watch?t=199&v=sbqMqb6FVMY&feature=youtu.be)

[Cornelius 2022: Decode 433.92 MHz weather station data](https://www.onetransistor.eu/2022/01/decode-433mhz-ask-signal.html)


a) WebSDR. Etäkäytä WebSDR-ohjelmaradiota, joka on kaukana sinusta ja kuuntele radioliikennettä. Radioliikenne tulee siepata niin, että radiovastaanotin on joko eri maassa tai vähintään 400 km paikasta, jossa teet tätä tehtävää. Käytä esimerkkinä julkista, suurelle yleisölle tarkoitettua viestiä, esimerkiksi yleisradiolähetystä. Kerro löytämäsi taajuus, aallonpituus ja modulaatio. Kuvaile askeleet ja ota ruutukaappaus. (Tehtävässä ei saa ilmaista sellaisen viestin sisältöä tai olemassaoloa, joka ei ole tarkoitettu julkiseksi. Voit sen sijaan kuvailla, miten sait julkisen radiolähetyksen kuulumaan kaiuttimistasi. Julkisten, esimerkiksi yleisradiolähetysten sisältöä saa tietysti kuvailla.)

b) rtl_433. Asenna rtl_433 automaattista analyysia varten. Kokeile, että voit ajaa sitä. './rtl_433' vastaa "rtl_433 version 25.02 branch..."

c) Automaattinen analyysi. Mitä tässä näytteessä tapahtuu? Mitä tunnisteita (id yms) löydät? Analysoi näyte 'rtl_433' ohjelmalla.

d) Too compex 16? Olet nauhoittanut näytteen 'urh' -ohjelmalla .complex16s-muodossa. Muunna näyte rtl_433-yhteensopivaan muotoon ja analysoi se. 

e) Ultimate. Asenna URH, the Ultimate Radio Hacker.


- Tarkastele näytettä. Siinä Nexan pistorasian kaukosäätimen valon 1 ON -nappia on painettu kolmesti. Käytä Ultimate Radio Hacker 'urh' -ohjelmaa.

f) Yleiskuva. Kuvaile näytettä yleisesti: kuinka pitkä, millä taajuudella, milloin nauhoitettu? Miltä näyte silmämääräisesti näyttää?

g) Bittistä. Demoduloi signaali niin, että saat raakabittejä. Mikä on oikea modulaatio? Miten pitkä yksi raakabitti on ajassa? Kuvaile tätä aikaa vertaamalla sitä johonkin. (Monissa singaaleissa on line encoding, eli lopullisia bittejä varten näitä "raakabittejä" on vielä käsiteltävä)

*Näytteet ladattavissa [Teron](https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/) sivuilta.*



# **x) Lue ja tiivistä. (Tässä x-alakohdassa ei tarvitse tehdä testejä tietokoneella, vain lukeminen tai kuunteleminen ja tiivistelmä riittää. Tiivistämiseen riittää muutama ranskalainen viiva.)**

[Hubacek 2019: Universal Radio Hacker SDR Tutorial on 433 MHz radio plugs (Video, alkaen 3:19 ja päättyen 7:40. Yhteensä noin 4 min.)](https://www.youtube.com/watch?t=199&v=sbqMqb6FVMY&feature=youtu.be)

- Video jossa demotaan URHn käyttöä. Samanlaista demoa kuin tunnillakin oli. Napattiin signaali ja katsottiin miltä se näytti URHissa. Eri asetuksia pystui muuttamaan ja katselemaan eri tuloksia.

[Cornelius 2022: Decode 433.92 MHz weather station data](https://www.onetransistor.eu/2022/01/decode-433mhz-ask-signal.html)

- Tekstissä tavoitteena on kääntää dataa sääasemasta joka toimii 433.92 megahetrzin taajuudella.
- Esitellään miten käytetään rtl_433 ohjelmistoa. Kuinka sillä decodataan dataa.
- URHlla otetaan dataa kiinni ja analysoidaan sitä.
- Analysoidaan myös mikä modulaatio on kyseessä.



# **a) WebSDR. Etäkäytä WebSDR-ohjelmaradiota, joka on kaukana sinusta ja kuuntele radioliikennettä. Radioliikenne tulee siepata niin, että radiovastaanotin on joko eri maassa tai vähintään 400 km paikasta, jossa teet tätä tehtävää. Käytä esimerkkinä julkista, suurelle yleisölle tarkoitettua viestiä, esimerkiksi yleisradiolähetystä. Kerro löytämäsi taajuus, aallonpituus ja modulaatio. Kuvaile askeleet ja ota ruutukaappaus.**

Googlailemalla löysin [Northern Utah WebSDR serverin](http://websdr1.sdrutah.org:8901/index1a.html)

![](https://github.com/user-attachments/assets/d8ff4187-f453-4186-b19c-3849fa8b55f6)

Aallonpituus on 1160.000 kHz. Käytössä Oli amplitudimodulaatio (AM).

Radiosta kuului ohjelma nimeltää "KSL News Radio". Ohjelmassa oli paikallisia uutisia (oletettavasti Utahista) sekä sääennusteita. Uutisissa oli mm. kadonnut nuori lapsi, sekä uutisia Trumpin päätöksistä. Uutisissa puhuttiin myös Matthew Perryn kuolemasta ja Perryn lääkärin oikeudenkäynnistä.


# **b) rtl_433. Asenna rtl_433 automaattista analyysia varten. Kokeile, että voit ajaa sitä. './rtl_433' vastaa "rtl_433 version 25.02 branch..."**

Käytössäni on Applen joten kokeillaan rtl_433 asentamista suoraan siihen. Virallisista github ohjeista löytyi komento `brew install rtl_433` joten ajetaan se.

Jostain syystä asennus ei onnistunut. 

Siirrytäänpä sitten virtualboxiin ja Debian virtuaalikoneeseen. Ajetaan siellä komento `sudo apt-get install rtl-433`.
  
![](https://github.com/user-attachments/assets/1123f976-16d1-4668-a651-315e1638468d)

Debianilla asennus onnistui helposti. Käytössä on siis versio 25.02.


# **c) Automaattinen analyysi. Mitä tässä näytteessä tapahtuu? Mitä tunnisteita (id yms) löydät? Analysoi näyte 'rtl_433' ohjelmalla.**

Näyte nimeltään `Converted_433.92M_2000k.cs8`

Ajetaan komento `rtl_433 -r Converted_433.92M_2000k.cs8. `

![](https://github.com/user-attachments/assets/cf67e3bf-6804-4776-ab3f-7a5bb072ce38)

Näytteestä ilmestyi jonkin verran dataa. Näytteestä löytyi kolme ari laitetta: Nexa-Security, Proove-Security ja KlikAanKlikUnit-Switch. Olisivatkohan nämä jotain turva/hälytyslaitteita. Jokaisessa laitteessa ID tai House kode on sama 8785315. Kaikki laitteet näyttäsivät olevan pois päältä. Channel ja Unit on jokaisessa myös sama 3.


# **d) Too compex 16? Olet nauhoittanut näytteen 'urh' -ohjelmalla .complex16s-muodossa. Muunna näyte rtl_433-yhteensopivaan muotoon ja analysoi se.**

Näyte nimeltään `Recorded-HackRF-20250411_183354-433_92MHz-2MSps-2MHz.complex16s`

Kyseinen tiedosto on väärässä muodossa joten muutetaan se oikeaan muotoon Teron vinkkien mukaisesti. Muutetaan pelkästään nimeä. Vaihdetaan ".complex16s" muoto "cs8" muotoon. Pelkästään tiedostonimi muuttui. 

Tämän jälkeen kokeillaan ajaa sama komento kuin edellisessä kohdassa: `rtl_433 -r Recorded-HackRF-20250411_183354-433_92MHz-2MSps-2MHz.cs8`

![](https://github.com/user-attachments/assets/34144cd3-6500-435d-8cbd-de2d96e59114)

Ja kappas näyte aukesi. Näyte sisälsi samaa informaatiota kuin aikaisempi näyte. Proove- ja Nexa-Security.

# **e) Ultimate. Asenna URH, the Ultimate Radio Hacker.**

Seurataan ohjeita suoraan teron vinkeistä:

`sudo apt-get update`

`sudo apt-get -y install pipx`

`pipx install urh`

`pipx ensurepath`

sulje ja avaa terminaali

`urh`

URH graafinen käyttöliittymä aukeaa

Mutta kohdassa `pipx install urh` tulikin ongelmia.

![](https://github.com/user-attachments/assets/7b1a6495-af7c-4b58-8297-5888bdd7d408)
Asennus ei onnistunutkaan.

Tutkitaan kohtaa jossa lukee "Full pip output in file:". Avataan kyseinen tiedosto.

![](https://github.com/user-attachments/assets/0a4dd089-fc9f-4073-a95f-c0463e509c82)

Siellä huomiota herätti kohta "You need Cython to build URH´s extentions!"

Kokeillaan komentoa `python3 -m pipx install cython`

![](https://github.com/user-attachments/assets/628eac8b-ccce-4dc1-bb89-e721b3d01fd8)

Jotain tapahtui onnistuneesti. Mutta ongelma ei siltikään ratkennut. 

Tässä vaiheessa katsotaan apua luokkakaverien raporteista. Seurataan Robin Niinementsin [rapottia](https://rbin.dev/diary/entries/diary.html?entry=VT25-008&week=Week%2049) sillä siellä näyttäisi olevan ratkaisu ongelmaan. 

URH perinteisessä asennuksessa näyttäisi olevan tällä hetkellä bugi, joten seurataan Robinin ohjeita URHin asentamiseen.

![](https://github.com/user-attachments/assets/edf44e7e-f7a1-4bef-8c8d-aca5e47816f1)

Ohjeita seuraamalla jäätiin silti jumiin samaan kohtaan. Cython on asennettu mutta silti URH ei toimi. Tässä vaiheessa teki mieli jo luovuttaa.

Kokeilin kuitenkin vielä kokeilla ajamalla komennon `python setup.py install` ja tämän avulla URH lähtikin toimimaan. Komento löytyi arvioidessani Santeri Vauramon [raporttia](https://santerivauramo.com/schoolworks/verkkoon-tunkeutuminen-ja-tiedustelu/h7/)

![](https://github.com/user-attachments/assets/d4c50d66-41e4-43b2-a6e6-d61e5841399d)

Komennolla `URH` sain vihdoin ohjelman auki. Avataan myös URHilla tehtävän näyte " 1-on-on-on-HackRF-20250412_113805-433_912MHz-2MSps-2MHz.complex16s"

# **f) Yleiskuva. Kuvaile näytettä yleisesti: kuinka pitkä, millä taajuudella, milloin nauhoitettu? Miltä näyte silmämääräisesti näyttää?**

![](https://github.com/user-attachments/assets/8133ff92-2a75-4f2b-b78d-c92ac28c8f08)

Silmämääräisesti näytteestä näkee heti kolme painallusta. Näytteestä on hieman vaikea ymmärtää muita asioita. Tieostonimestä voisi päätellä että nauhoitus on tehty 4.12.2025. Näytteen kesto on noin 5,47 sekuntia.

# **g) Bittistä. Demoduloi signaali niin, että saat raakabittejä. Mikä on oikea modulaatio? Miten pitkä yksi raakabitti on ajassa? Kuvaile tätä aikaa vertaamalla sitä johonkin. (Monissa singaaleissa on line encoding, eli lopullisia bittejä varten näitä "raakabittejä" on vielä käsiteltävä)**

Oikea modulaatio taitaa olla ASK. Raakabitti on noin 520 mikrosekuntia pitkä. Tunnissa on 3 600 000 000 mikrosekuntia.





# Lähteet
- Tero Karvinen, 2025, Verkkoon tunkeutuminen ja tiedustelu: https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/
- Northern Utah WebSDR, http://websdr1.sdrutah.org:8901/index1a.html
- GitHub, merbanan, rtl_433: https://github.com/merbanan/rtl_433
- Robin Niiniments, H7 - Aaltoja Harjaamassa: https://rbin.dev/diary/entries/diary.html?entry=VT25-008&week=Week%2049
- Santeri Vauramo h7 Aaltoja Harjaamassa: https://santerivauramo.com/schoolworks/verkkoon-tunkeutuminen-ja-tiedustelu/h7/
