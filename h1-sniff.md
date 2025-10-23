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


**x) Lue ja tiivistä.**


Karvinen 2025: [Wireshark - Getting Started](https://terokarvinen.com/wireshark-getting-started/)

- Ohjeet kuinka asentaa wireshark linuxiin käyttäen komentokehotetta. Hyvin selkeät ohjeet, joita todennäköisesti hyödynnän tulevaisuudessa, vaikka wiresharkkia on tullut ennenkin asenneltua.
- Sisältää myös vinkkejä siihen miten wiresharkkia käytetään. Esimerkiksi -pcap luominen ja niiden käsittely.

Karvinen 2025: [Network Interface Names on Linux](https://terokarvinen.com/network-interface-linux/)

- Network Interface Names ovat nimiä virtuaalisille ns "verkkokorteille". Kun virtuaalikoneessa ei voi olla fyysistä verkkokorttia. "en" tarkoittaa "Wired Ethernet. "wl" tarkoittaa Wlania. "lo" tarkoittaa Loopback Adapter.
- Omia interfaceja voi tarkastella komennoilla `ip a` ja `ip route`



**a) Linux. Asenna Debian tai Kali Linux virtuaalikoneeseen.**

Tätäkin on tehty jo aikaisemmin. Seurataan [Karvisen ohjetta](https://terokarvinen.com/2021/install-debian-on-virtualbox/) debianin asennukseen. 

Alempana valokuva debianista asentumassa.

[debianasennus](https://github.com/user-attachments/assets/615cd65d-005d-4e27-958e-ab8f46bb8083)


Kali-linux tuli asennettua viime kurssilla. Joten sen asentamiseen voidaan seurata omaa [vanhaa raporttia](https://github.com/juliusjantti/Tunkeutumistestaus/blob/main/h1%20Hacker's%20Journey.md) viimekurssilta. Kohta a) asennetaan Kali Linux virtuaalikoneeseen.


