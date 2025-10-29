# h2 Violetti - Tehtävät

Kaikissa kohdissa edellytetään analyysia ja selitystä. Selvitä ja selitä siis komentojen ja komentoriviparametrien merkitys. Selitä, mitä tulokset tarkoittavat; ja mitä niistä tulisi ymmärtää. Lue vinkit, ennenkuin aloitat.

x) Lue ja vastaa lyhyesti kysymyksiin. Tässä alakohdassa x ei tällä kertaa tarvitse lukea artikkeleita kokonaan, ei tarvitse tiivistää niitä, eikä tehdä testejä koneella.
- Selitä tuskan pyramidin idea 1-2 virkkeellä. Bianco 2013: Pyramid of Pain. (Katso eritoten pyramidin kuvaa.)
- Selitä timanttimallin (Diamond Model) idea 1-2 virkkeellä. Tekijä esittelee sen aika juhlallisesti, voit myös etsiä yksinkertaisempia artikkeleita hakukoneella tai kelata suoraan timantin kuvaan. Caltagirone et al 2013: Diamond Model

a) Apache log. Asenna Apache-weppipalvelin paikalliselle virtuaalikoneellesi. Surffaa palvelimellesi salaamattomalla HTTP-yhteydellä, http://localhost . Etsi omaa sivulataustasi vastaava lokirivi. Analysoi yksi tällainen lokirivi, eli selitä sen kaikki kohdat. (Jos Apache ei ole kovin tuttu, voit tätä tehtävää varten vain asentaa sen ja testata oletusweppisivulla. Eli ei tarvitse tehdä omia kotisvuja tms.)

b) Nmapped. Porttiskannaa oma weppipalvelimesi käyttäen localhost-osoitetta ja 'nmap -A' päällä. Selitä tulokset. (Pelkkä http-portti 80/tcp riittää)

c) Skriptit. Mitkä skriptit olivat automaattisesti päällä, kun käytit "-A" parametria? (Näkyy avoimien porttinumeroiden alta, http-blah, http-blöh...).

d) Jäljet lokissa. Etsi weppipalvelimen lokeista jäljet porttiskannauksesta (NSE eli Nmap Scripting Engine -skripteistä skannauksessa). Löydätkö sanan "nmap" isolla tai pienellä? Selitä osumat. Millaisilla hauilla tai säännöillä voisit tunnistaa porttiskannauksen jostain muusta lokista, jos se on niin laaja, että et pysty lukemaan itse kaikkia rivejä?

e) Wire sharking. Sieppaa verkkoliikenne porttiskannatessa Wiresharkilla. Huomaa, että localhost käyttää "Loopback adapter" eli "lo". Tallenna pcap. Etsi kohdat, joilla on sana "nmap" ja kommentoi niitä. Jokaisen paketin jokaista kohtaa ei tarvitse analysoida, yleisempi tarkastelu riittää.

f) Net grep. Sieppaa verkkoliikenne 'ngrep' komennolla ja näytä kohdat, joissa on sana "nmap".

g) Agentti. Vaihda nmap:n user-agent niin, että se näyttää tavalliselta weppiselaimelta.

h) Pienemmät jäljet. Porttiskannaa weppipalvelimesi uudelleen localhost-osoitteella. Tarkastele sekä Apachen lokia että siepattua verkkoliikennettä. Mikä on muuttunut, kun vaihdoit user-agent:n? Löytyykö lokista edelleen tekstijono "nmap"?

i) Hieman vaikeampi: LoWeR ChEcK. Poista skritiskannauksesta viimeinenkin "nmap" -teksti. Etsi löytämääsi tekstiä /usr/share/nmap -hakemistosta ja korvaa se toisella. Tee porttiskannaus ja tarkista, että "nmap" ei näy isolla eikä pienellä kirjoitettuna Apachen lokissa eikä siepatussa verkkoliikenteessä. (Tässä tehtävässä voit muokata suoraan lua-skriptejä /usr/share/nmap alta, 'sudoedit'. Muokatun version paketoiminen siis rajataan ulos tehtävästä.)

j) Vapaaehtoinen, vaikea: Invisible, invincible. Etsi jokin toinen nmap:n skripti, jonka verkkoliikenteessä esiintyy merkkijono "nmap" isolla tai pienellä. Muuta nmap:n koodia niin, että tuo merkkijono ei enää näy verkkoliikenteessä.


## Vastaukset

# **x) Lue ja vastaa lyhyesti kysymyksiin. Tässä alakohdassa x ei tällä kertaa tarvitse lukea artikkeleita kokonaan, ei tarvitse tiivistää niitä, eikä tehdä testejä koneella.**

- Tuskan Pyramidi ([Pyramid of pain(https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html)]) on luotu kuvaamaan sitä kuinka paljon haittaa hyökkääjälle koituu erilaisten hyökkäyksien torjumisesta. Kuvassa alimman kerroksen indikaattorien torjuminen tuottaa vähiten kipua, ja ylimmän indikaattorin torjuminen tuottaa eniten päänvaivaa. Tekstin pointtina on että jos jostain hyökkäyksestä ilmenee indikaattoreita, niihin pitää reagoida välittömästi.
- Timanttimalli tai [Diamond Model](https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf) on malli jonka avulla voidaan ymmärtää kyberturvallisuusuhkia tai hyökkäyksiä ([*lähde*](https://kravensecurity.com/diamond-model-analysis/)). Mallissa kuvataan hyökkääjä, uhri, infrastruktuuri ja toimintatapa. Jokainen hyökkäys sisältää nämä neljä komponenttia.



# **a) Apache log. Asenna Apache-weppipalvelin paikalliselle virtuaalikoneellesi. Surffaa palvelimellesi salaamattomalla HTTP-yhteydellä, http://localhost . Etsi omaa sivulataustasi vastaava lokirivi. Analysoi yksi tällainen lokirivi, eli selitä sen kaikki kohdat. (Jos Apache ei ole kovin tuttu, voit tätä tehtävää varten vain asentaa sen ja testata oletusweppisivulla. Eli ei tarvitse tehdä omia kotisvuja tms.)**

Aloitetaan asentaminen siirtymällä virtuaalikoneelle ja ajamalla muutama komento. Apache2 voidaan asentaa ajamalla koento `sudo apt install apache2`. Annetaan sen latautua, jonka jälkeen voidaan käynnistää apache ajamalla komento `sudo systemctl start apache2`. Sitten katsotaan onko palvelin ylhäällä ajamalla komento `systemctl status apache2`

![](https://github.com/user-attachments/assets/350c4feb-86a5-46c8-a4d1-e9fa2f483aa8)

Näyttäisi toimivan, mutta kokeillaan vielä avata selaimessa oma `localhost` sivu. 

![](https://github.com/user-attachments/assets/75f7baab-7db2-4e1e-9a20-2953fff561c5)

Apache oletussivu avautuu. Sitten etsimään omaa sivulatausta vastaavaa lokiriviä. Tehtävänannon vinkeissä lukee että lokit löytyvät hakemistosta /var/log/apache2 tiedostosta access.log. Kokeillaan avata se. Käytetään taas vinkeistä löytyvää komentoa `sudo tail -F /var/log/apache2/access.log`.  

![](https://github.com/user-attachments/assets/0c747848-6f8d-486b-8e52-ae46baa160b8)

Ylhäällä kuva lokeista. Omaa localhost sivua päivittämällä lokiin tulee uusia rivejä. Oletettavasti kaikki lokissa olevat rivit ovat omia käyntejä. 

Ensimmäisenä lukee IP osoite. Kaksi tavuviivaa josta ensimmäinen on clientin identiteetti. Tämä jää usein viivaksi. Toinen viiva pitäisi olla verkksoivun hakijan User ID. Tämä on kuitenkin tyhjä. Tämän jälkeen aikaleima. Seuraavaksi millainen pyyntö ja mitä pyydetään. Numero "200" on HTTP status code, ja luku "3383" on tiedostokoko joka haettiin. ([lähde](https://www.sumologic.com/blog/apache-access-log)) Tekstin loppupätkässä on tietoa käyttäjän selaimesta.

# **b) Nmapped. Porttiskannaa oma weppipalvelimesi käyttäen localhost-osoitetta ja 'nmap -A' päällä. Selitä tulokset. (Pelkkä http-portti 80/tcp riittää)**

Tässä virtuaalikoneessa ei ole vielä nmappia asennettuna joten asennetaan se komennolla `sudo apt-get install nmap -y`

Tehdään ennen porttiskannauksen aloitusta testi että tietokone ei ole kiinni internetissä. 

![](https://github.com/user-attachments/assets/a1450e87-761b-4254-97c6-80306b200462)

Hyvältä näyttää.

Kokeillaan porttiskannausta `sudo nmap -A localhost`

![](https://github.com/user-attachments/assets/8ae378a6-61e5-4f18-b05f-c3a13e4cf958)

Porttiskannauksessa löytyi kaksi porttia. Aiemmin pystytetty Apache2 palvelin, sekä myös portti 631. Nopealla googlauksella portti 631 on IPP (Internet Printing Protocol) portti. Apache palvelin on portissa 80 kuten pitääkin.

# **c) Skriptit. Mitkä skriptit olivat automaattisesti päällä, kun käytit "-A" parametria? (Näkyy avoimien porttinumeroiden alta, http-blah, http-blöh...).**

![](https://github.com/user-attachments/assets/f44b93a0-4c37-423a-9528-262fa8248b6c)

Kuvankaappaus aikaisemmasta kohdasta, mutta ympyröitynä tehtävänannossa pyydetyt skriptit. Päällä olevia skriptejä oli `http-title`, `http-server-header`, sekä `http-robots.txt`.

Esimerkiksi `http-title` kertoo weppisivun otsikon.

![](https://github.com/user-attachments/assets/5ae3c033-79da-4308-9a31-8fc89b5b7656)

Nopealla googlailulla `http-robots.txt` on tekstitiedosto joka ohjaa tai rajoittaa botteja.

# **d) Jäljet lokissa. Etsi weppipalvelimen lokeista jäljet porttiskannauksesta (NSE eli Nmap Scripting Engine -skripteistä skannauksessa). Löydätkö sanan "nmap" isolla tai pienellä? Selitä osumat. Millaisilla hauilla tai säännöillä voisit tunnistaa porttiskannauksen jostain muusta lokista, jos se on niin laaja, että et pysty lukemaan itse kaikkia rivejä?**

Ajetaan uudestaan komento `sudo tail -F /var/log/apache2/access.log` ja katsotaan onko lokiin tullut uusia lisäyksiä. 


![](https://github.com/user-attachments/assets/50a21da3-e880-4a08-92be-f5838ce13587)

Siellä näyttäisi olevan lisää kohtia. Esiin paistaa heti NSE (Nmap Scripting Engine). Lokissa näkyy myös URL 'https://nmap.org/book/nse.html'. IP osoite on edelleen sama kuin aiemmassa tehtävässä, koska suoritan itse porttiskannausta omaan virtuaalikoneeseen. 

NSE on nmapin oma ominaisuus jolla käyttäjä voi kirjoittaa ja jakaa omia skriptejä ([lähde](https://nmap.org/book/nse.html)). Skriptejä voidaan aktivoida `-sC` optiolla. 

Suuremmasta lokista voisi etsiä kohtia juuri hakusanoilla 'nmap' tai 'Nmap Sctipting Engine' tai 'https://nmap.org/book/nse.html'.










# Lähteet
- Tero Karvinen, Verkkoon tunkeutuminen ja tiedostelu, https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/
- Akamai Developer, Apache Basics Tutorial, https://www.youtube.com/watch?v=1CDxpAzvLKY
- Sumologic.com, Understanding the Apache access log, https://www.sumologic.com/blog/apache-access-log
