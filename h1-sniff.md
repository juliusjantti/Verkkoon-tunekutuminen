# h1 sniff - tehtävät


x) Lue ja tiivistä. (Tässä x-alakohdassa ei tarvitse tehdä testejä tietokoneella, vain lukeminen tai kuunteleminen ja tiivistelmä riittää. Tiivistämiseen riittää muutama ranskalainen viiva.)
Karvinen 2025: [Wireshark - Getting Started](https://terokarvinen.com/wireshark-getting-started/)
Karvinen 2025: [Network Interface Names on Linux](https://terokarvinen.com/network-interface-linux/)

a) Linux. Asenna Debian tai Kali Linux virtuaalikoneeseen. (Tätä alakohtaa ei poikkeuksellisesti tarvitse raportoida, jos sinulla ei ole mitään ongelmia. Jos on mitään haasteita, tee täsmällinen raportti)

b) Ei voi kalastaa. Osoita, että pystyt katkaisemaan ja palauttamaan virtuaalikoneen Internet-yhteyden.

c) Wireshark. Asenna Wireshark. Sieppaa liikennettä Wiresharkilla. (Vain omaa liikennettäsi. Voit käyttää tähän esimerkiksi virtuaalikonetta).

d) Oikeesti TCP/IP. Osoita TCP/IP-mallin neljä kerrosta yhdestä siepatusta paketista. Voit selityksen tueksi laatikoida ne ruutukaappauksesta. (Voit käyttää vastauksesi osana ruutukaappaustasi h0-tehtävästä, mutta tässä tehtävässä tarvitaan myös sanallinen selitys.)

e) Mitäs tuli surffattua? Avaa surfing-secure.pcap. Tutustu siihen pintapuolisesti ja kuvaile, millainen kaappaus on kyseessä. Tässä siis vain lyhyesti ja yleisellä tasolla. Voit esimerkiksi vilkaista, montako konetta näkyy, mitä protokollia pistää silmään. Määrästä voit arvioida esimerkiksi pakettien lukumäärää, kaappauksen kokoa ja kestoa.

f) Vapaaehtoinen, vaikea: Mitä selainta käyttäjä käyttää? surfing-secure.pcap (Päivitys 2025-03-31 w14 ma - muutin tehtävän vapaaehtoiseksi Giang:n suosituksesta)

g) Minkä merkkinen verkkokortti käyttäjällä on? surfing-secure.pcap

h) Millä weppipalvelimella käyttäjä on surffaillut? surfing-secure.pcap
Huonoja uutisia: yhteys on suojattu TLS-salauksella.

i) Analyysi. Sieppaa pieni määrä omaa liikennettäsi. Analysoi se, eli selitä mahdollisimman perusteellisesti, mitä tapahtuu. (Tässä pääpaino on siis analyysillä ja selityksellä, joten liikennettä kannattaa ottaa tarkasteluun todella vähän - vaikka vain pari pakettia. Gurut huomio: Selitä myös mielestäsi yksinkertaiset asiat.)


# **x) Lue ja tiivistä.**


Karvinen 2025: [Wireshark - Getting Started](https://terokarvinen.com/wireshark-getting-started/)

- Ohjeet kuinka asentaa wireshark linuxiin käyttäen komentokehotetta. Hyvin selkeät ohjeet, joita todennäköisesti hyödynnän tulevaisuudessa, vaikka wiresharkkia on tullut ennenkin asenneltua.
- Sisältää myös vinkkejä siihen miten wiresharkkia käytetään. Esimerkiksi -pcap luominen ja niiden käsittely.

Karvinen 2025: [Network Interface Names on Linux](https://terokarvinen.com/network-interface-linux/)

- Network Interface Names ovat nimiä virtuaalisille ns "verkkokorteille". Kun virtuaalikoneessa ei voi olla fyysistä verkkokorttia. "en" tarkoittaa "Wired Ethernet. "wl" tarkoittaa Wlania. "lo" tarkoittaa Loopback Adapter.
- Omia interfaceja voi tarkastella komennoilla `ip a` ja `ip route`



# **a) Linux. Asenna Debian tai Kali Linux virtuaalikoneeseen.**

Tätäkin on tehty jo aikaisemmin. Seurataan [Karvisen ohjetta](https://terokarvinen.com/2021/install-debian-on-virtualbox/) debianin asennukseen. 

Alempana valokuva debianista asentumassa.

![debianasennus](https://github.com/user-attachments/assets/615cd65d-005d-4e27-958e-ab8f46bb8083)

Ja tässä debian näyttäisi toimivan. Ja näyttäisi olevan myös yhteydessä internettiin. 

![](https://github.com/user-attachments/assets/9491a9c0-77ff-42af-9e49-386191e4d71a)

Kali-linux tuli asennettua viime kurssilla. Joten sen asentamiseen voidaan seurata omaa [vanhaa raporttia](https://github.com/juliusjantti/Tunkeutumistestaus/blob/main/h1%20Hacker's%20Journey.md) viimekurssilta. Kohta a) asennetaan Kali Linux virtuaalikoneeseen.


# **b) Ei voi kalastaa. Osoita, että pystyt katkaisemaan ja palauttamaan virtuaalikoneen Internet-yhteyden.**

Otetaan virtuaalikoneen asetuksista "cable connected" kohta irti. Eli vedetään ns töpseli seinästä.

![](https://github.com/user-attachments/assets/42f5ef95-3552-4402-a7b3-8fa0105731e3)

Yritetään pingata uudestaan johdon irroittamisen jälkeen ja nähdään että yhteyttä ei ole. Tietokone ei ole netissä.

![](https://github.com/user-attachments/assets/bfa0f0b9-eaca-4e5f-b4d8-9f482211279a)

Ja vielä kun yhdistetään johto takaisin virtuaalikoneeseen se saa yhteyden internettiin.


# **c) Wireshark. Asenna Wireshark. Sieppaa liikennettä Wiresharkilla. (Vain omaa liikennettäsi. Voit käyttää tähän esimerkiksi virtuaalikonetta).**

Seurataan aikaisemman tehtäväkohdan ohjeita wiresharkin asennuksesta. 

Asennetaan wireshark komennoilla:

`sudo apt-get update`
`sudo apt-get install wireshark`

Virtuaalikone herjasi jotain ongelmaa, ajetaan komento mikä näkyi komentokehotteessa.


![](https://github.com/user-attachments/assets/050f104d-a9dc-430d-8e82-fa7efce62b8a)

Jotain tapahtui. Ajetaan asennuskomento uudestaan.


![](https://github.com/user-attachments/assets/4d4cc984-43b9-4286-89d6-8558e2743557)

Päästiin eteenpäin. Ohjeessa suositeltiin valitsemaan ohta "<yes>". Wiresharkin lataus onnistui. Seurataan ohjetta.

Awataan wireshark komennolla `wireshark`, ja kokeillaan napat liikennettä. Pingataan 8.8.8.8 ja katsotaan tuleeko wiresharkiin mitään.

![](https://github.com/user-attachments/assets/ddb62440-e04a-4947-8241-d487972e7c92)

Siellähän näkyy liikennettä.


# **d) Oikeesti TCP/IP. Osoita TCP/IP-mallin neljä kerrosta yhdestä siepatusta paketista. Voit selityksen tueksi laatikoida ne ruutukaappauksesta. (Voit käyttää vastauksesi osana ruutukaappaustasi h0-tehtävästä, mutta tässä tehtävässä tarvitaan myös sanallinen selitys.)**

Tässä kuva aikaisemmasta tehtävästä. 

![](https://github.com/user-attachments/assets/28ade437-19af-4a02-8592-8c2b28327aba)

Kuvassa näkyy Link- Internet- ja Transport layerit. Link layer sisältää MAC-osoitteita. Internet layerin tunnistaa IPv4 osotteista. Transport layerissa näkyy TCP protokolla ja portit.




## Lähteet

- Markdownguide.org, Markdown Cheat sheet, https://www.markdownguide.org/cheat-sheet/
- Tero Karvinen, Network Interface names on Linux, https://terokarvinen.com/network-interface-linux/
- Tero Karvinen, Wireshark - Getting Started, https://terokarvinen.com/wireshark-getting-started/
- Julius Jäntti, GitHub, h1 Hackers Journey, https://github.com/juliusjantti/Tunkeutumistestaus/blob/main/h1%20Hacker's%20Journey.md
