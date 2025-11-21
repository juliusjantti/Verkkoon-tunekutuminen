# h5 Kotitehtävät


a) Tutustu seuraavaan työkaluun: [Evilginx2](https://github.com/kgretzky/evilginx2)

Vastaa seuraaviin kysymyksiin:

 - Asensitko työkalun, jos asensit niin kirjoita miten sen teit.
 - Mitä teit työkalun kanssa?
 - Onnistuitko huijaamaan liikennettä?
   
b) Sinulla on käytössäsi mininet ympäristö. Luo ympäristö, jossa voit tehdä TCP SYN-Flood hyökkäyksen.
Kirjoita miten loit mininet ympäristön ja miten toteutit hyökkäyksen.

# **a) Tutustu työkaluun**


Tutustutaan työkaluun ensin lukemalla Github README tiedosto läpi. Tämän jälkeen yritetään asentaa kyseinen sovellus Debian viftuaalikoneelle. Luetaan ohjeet [Local Installation Guidesta](https://help.evilginx.com/pro/installation/local)

![](https://github.com/user-attachments/assets/a1d86389-91df-4c81-ac98-58007c7aa84e)

Jotta voidaan asentaa Evilginx täytyy ensin asentaa node.js, ja jotta voidaan asentaa node.js täytyy ensin asentaa NVM. Joten aloitetaan NVMstä. Ohjeet sen asentamiseen löytyivät [täältä](https://github.com/nvm-sh/nvm?tab=readme-ov-file#installing-and-updating)

![](https://github.com/user-attachments/assets/339967d2-29cc-41a7-a79c-0f011d2d87a1)

NVM ja node.js on asennettu. Seurataan ohjeita.

Tässä vaiheessa huomataan että ollaan asentamassa Evinginx Pro versiota joka ei taida onnistua ilmaiseksi. Asentamiseen tarvitaan "Breakdev Red" käyttäjä sekä jonkinlainen Server License.

Siirrytään [Evilginx community](https://help.evilginx.com/community) puolelle josta mahdolliset ohjeet löytyisivät. Siellä ohjeistetaan rakentamaan Evilginx itse. Joten ladataan Evilginx Github sivulta tarvittavat tiedostot.

Asennetaan ohjeissa esitetty Golang, sekä Node.js joka jo tuli aikaisemmin asennettua. Tämän jälkeen ajetaan Evilginx hakemistossa `make` komento. 

Tämän jälkeen hakemistoon ilmestyi uusi "build" hakemisto.

![](https://github.com/user-attachments/assets/3a5d238f-d20c-4d8c-b910-2a10eaf47707)

Siirrytäään sinne ja sieltä näyttäisi Evilginx löytyvän.


![](https://github.com/user-attachments/assets/2810992e-16b2-4d2e-bad9-cb850185ee15)

Evilginx näyttäisi toimivan. 





# **Lähteet**

- Evilginx, Local Installation Guide: https://help.evilginx.com/pro/installation/local
- Github, Node Version Manager: https://github.com/nvm-sh/nvm?tab=readme-ov-file#installing-and-updating
- 
