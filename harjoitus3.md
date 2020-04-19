# Palvelinten hallinta ICT4TN022-3005 Harjoitus 3

###### Tehtävän suorittaminen aloitettu 19.4.2020 klo. 15:30

Laitteen/alustan tiedot, jolla tehtävä suoritettiin:

* Oracle VirtualBox 6.1.4
* Xubuntu 18.04.03 LTS (+ VirtualBox guest additions)
* 4GB RAM
* 8GB Levytilaa (dynaaminen)

Aloitin tehtävän ajamalla komennon
`sudo apt-get update`
Sekä testasin minionin toimivuuden komennolla
`sudo salt '*' cmd.run 'whoami'`

#### a) MarkDown. Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän.

Aloitin harjoituksen luomalla uuden repon githubin verkkosivulla.
 Annoin tälle repolle luovasti nimen "palvelintenhallintaharjoitus3".
 Valitsin vielä, että github luo tälle repolle valmiiksi README-tiedoston, sekä lisenssiksi GNU GPL v3.0 -lisenssin.
Tämän jälkeen sain seuraavan näkymän esiin selaimeen:
KUVA
Kloonasin tämän jälkeen luomani repon virtuaalikoneelle komennolla
`git clone https://github.com/tommygratschew/palvelintenhallintaharjoitus3.git`, joka kloonasi kaikki repossa olleet
tiedostot repon nimiseen kansioon käyttäjän kotihakemistoon. Siirryin tähän kansioon komennolla
`cd palvelintenhallintaharjoitus3/` ja loin uuden markdown-tiedoston komennolla `nano harjoitus3.md`. Aloitin
raportin kirjoittamista tähän tiedostoon, jonka jälkeen tallensin sen ja siirsin sen githubbiin komennolla
`git add . && git commit; git pull && git push`. Pienen taistelun sisäänkirjautumistietojen ja access tokenien kanssa,
sain kuin sainkin tiedoston siirrettyä ja sitä pystyi tarkastelemaan repon github-sivulla.
