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
`git add . && git commit; git pull && git push` (komento päivittää samalla myös muiden repon käyttäjien tekemät muutokset omalle koneelle). Pienen taistelun sisäänkirjautumistietojen ja access tokenien kanssa,
sain kuin sainkin tiedoston siirrettyä ja sitä pystyi tarkastelemaan repon github-sivulla. Ajoin tässä kohtaa myös 
komennon `git config --global credential.helper "cache --timeout=3600"` Tero Karvisen [ohjeesta](http://terokarvinen.com/2016/publish-your-project-with-github), jotta minun ei tarvinnut jokaista committia tehdessäni kirjoittaa kirjautumistietoja uudestaan.
KUVA
Huomasin, että kaikki kirjoittamani asiast eivät olleet menneet sellaiseen muotoiluun kun olisin toivonut.
Löysinkin [cheatsheetin](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet), jonka avulla sain muokattua
muotoilun haluamaani muotoon, jolloin se näytti tältä
KUVAT

#### d) Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.

* `git log`

log-komento näyttää repoon tehdyt muutokset/commitit. Muutoslokista selviää jokaisen muutoksen token, muutoksen tehnyt henkilö (author),
muutoksen tarkka aika (date) sekä muutoksentekijän jättämä kommentti muutoksesta (esim. "Raportointia")
KUVA

* `git diff`

diff-komennolla voidaan verrata miten ja missä tiedostoissa on eroja githubissa oleviin tiedostoihin verrattuna.
KUVA
Esimerkiksi en commitannut vielä viimeisimpiä muutoksia raporttiin, jolloin diff-komento näytti nämä eroavat rivit + -merkillä.

* `git blame`

blame-komennolla selviää, kuka on kirjoittany minkäkin rivin kustakin tiedostosta. Esimerkiksi ajamalla komennon `git blame harjoitus3.md` 
terminaalissa näkyy kyseisen tiedoston jokainen rivi numeroituna, sen sisältö, kirjoittaja ja aikaleima.
KUVA

#### e) Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset –hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

Kirjoitin raportin tiedostoon "TYHMÄ MUUTOS" ja tallensin tiedoston.
KUVA
Tämän jäleen ajoin komennon `git reset --hard`, joka antoi seuraavan ilmoituksen
KUVA
Eli muutokset oltiin muutettu takaisin viimeisimpään committiin.

