# h4 NFC ja RFID

## Tehtävät

1. Tarkastele käytössäsi olevia RFID tuotteita, mieti miten hyvin olet suojautunut RFID urkinnalta?
   
2. Tutustu APDU komentojen rakenteeseen (voit käyttää tekoälyä tutustumiseen)
   
3. Tutki ja kerro minkä mielenkiintoisen RFID hakkerointi uutiset löysit. (Vinkki, useimmat liittyvät henkilökortteihin)




# **1. Tarkastele käytössäsi olevia RFID tuotteita, mieti miten hyvin olet suojautunut RFID urkinnalta?**

Alustavasti pohtiessa mieleen ei tule kovin montaa RFID tuotetta jota itse käyttäisi jatkuvasti. Ensimmäisenä tulee mieleen tietenkin aikaisemmalla tunnilla tehty virtuaalinen käyntikortti.

![IMG_5700](https://github.com/user-attachments/assets/73c74980-ce5a-439a-8b30-bcd97119d0a0)

Valokuva itse kortista.

![](https://github.com/user-attachments/assets/2566b938-f730-43e8-bed8-279c90ca8f34)

Kortin tiedot luettaessa se `NFC Tools` sovelluksella.

Skannaamalla kortin pääsee käyttäjä katselemaan virtuaalista käyntikorttia. Kortti vie osoitteeseen [Tapni.com/juliusjäntti](https://tapni.com/juliusjantti).

Muita tuotteita mitä itseltä löytyy on lompakosta löytyvät erilaiset kortit: pankkikortti, erilaiset kauppojen bonuskortit, sekä henkilökortti. Lisäksi työpaikan avaimena tomiva kulkukortti. Kavereillani löytyy avaimista erilaisia lähiluku mahdollisuuksia, mutta itse operoin vielä perinteisellä ja mekaanisella avaimella.

RFID tuotteiden suojaamista en ole erityiseti ajatellut. Joten en myöskään ole erittäin suojautunut. Suurin osa korteistani asuu lompakossani, joka taas on yleensä taskussa. Tasku ei ole mitenkään erityisen suojattu joten esimerkiksi väkijoukossa omien korttien urkinta ei todennäköisesti olisi kovin hankalaa. Lisäksi lompakko on perinteinen nahkalompakko.
Työkortin urkinta on hieman hankalampaa sillä kortti on mukana ainoastaan silloin kun olen matkalla töihin. Muuten se pysyy kotona, josta urkkiminen on melko hankalaa. RFID urkinnalta 
voisi suojautua mahdollisesti paremmin pitämällä RFID tuotteita paremmassa paikassa. Mutta onko tämä sitten käytännöllistä. Toki kortteja voisi säilyttää erilaisissa RFID suojatuissa koteloisssa jotka hankaloittavat etälukua.

# **2. Tutustu APDU komentojen rakenteeseen (voit käyttää tekoälyä tutustumiseen)**

CardLogix [Application Protocol Data Unit](https://www.cardlogix.com/glossary/apdu-application-protocol-data-unit-smart-card/)

APDUt ovat komentoja joita käytetään korttien ja kortinlukijoiden väliseen kommunikointiin. Komennot koostuvat käsky- ja vastausviesteistä. (Comman and Response messages.) Yleensä puhutaan käsky- ja vastauspareista.

Lista käytetyimmistä APDU komennoista:

SELECT FILE (0x00A4)

READ BINARY (0x00B0)

UPDATE BINARY (0x00D6)

READ RECORDS (0x00B2)

UPDATE RECORDS (0x00DC)

APPEND RECORD (0x00E2)

VERIFY (0x0020)

CHANGE REFERENCE DATA (0x0024)

RESET RETRY COUNTER (0x002C)

GET CHALLENGE (0x0084)

INTERNAL AUTHENTICATE (0x0088)

EXTERNAL AUTHENTICATE (0x0082)

TERMINATE CARD USAGE (0x826E)

ERASE BINARY (0x00DA)

ERASE RECORDS (0x00DC)

(Lähde: CardLogix)

# **3. Tutki ja kerro minkä mielenkiintoisen RFID hakkerointi uutiset löysit. (Vinkki, useimmat liittyvät henkilökortteihin)**

Helsingin Sanomat [Järjestä kortit lompakon sisällä näin, jos et halua turhaan leimautua varkaaksi marketin ovella](https://www.hs.fi/suomi/art-2000010980999.html).

Artikkelissa puhutaan siitä miten erilaiset etäluetttavat kortit saattavat aiheuttaa hälytyksen kaupan kassoilla. Syynä tähän on se että päällekkäin säilytetyt kortit luovat vahvemman signaalin, ja usein signaali on sama kuin kaupan porteissa käytetty varashälyttimen signaali. Luottokortit eivät yleensä ole syyllisiä tähän ongelmaan. vaan syypäänä on etäluettavat sali- tai bussikortit. Artikkelissa suositellaan säilyttämään 
tämänlaisia kortteja lompakon eri taskuissa. Tai hälytyksen voi myös vaihtoehtoisesti välttää hankkimalla RFID-suojatun lompakon.

Hälytyksiä aiheuttaa artikkelin mukaan myös usein päällä oleviin vaatteisiin unohtunut pesulappuihin integroitu hälytin. 




# Lähteet

- CardLoxiz, Application Protocol Data Unit: https://www.cardlogix.com/glossary/apdu-application-protocol-data-unit-smart-card/
- Helsingin Sanomat, Järjestä kortit lompakon sisällä näin, jos et halua turhaan leimautua varkaaksi marketin ovella: https://www.hs.fi/suomi/art-2000010980999.html
- Wakdev, NFC Tools(iPhonelle): https://apps.apple.com/us/app/nfc-tools/id1252962749 
