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
![1]
Kloonasin tämän jälkeen luomani repon virtuaalikoneelle komennolla
`git clone https://github.com/tommygratschew/palvelintenhallintaharjoitus3.git`, joka kloonasi kaikki repossa olleet
tiedostot repon nimiseen kansioon käyttäjän kotihakemistoon. Siirryin tähän kansioon komennolla
`cd palvelintenhallintaharjoitus3/` ja loin uuden markdown-tiedoston komennolla `nano harjoitus3.md`. Aloitin
raportin kirjoittamista tähän tiedostoon, jonka jälkeen tallensin sen ja siirsin sen githubbiin komennolla
`git add . && git commit; git pull && git push` (komento päivittää samalla myös muiden repon käyttäjien tekemät muutokset omalle koneelle). Pienen taistelun sisäänkirjautumistietojen ja access tokenien kanssa,
sain kuin sainkin tiedoston siirrettyä ja sitä pystyi tarkastelemaan repon github-sivulla. Ajoin tässä kohtaa myös 
komennon `git config --global credential.helper "cache --timeout=3600"` Tero Karvisen [ohjeesta](http://terokarvinen.com/2016/publish-your-project-with-github), jotta minun ei tarvinnut jokaista committia tehdessäni kirjoittaa kirjautumistietoja uudestaan.
![2]
![3]
Huomasin, että kaikki kirjoittamani asiast eivät olleet menneet sellaiseen muotoiluun kun olisin toivonut.
Löysinkin [cheatsheetin](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet), jonka avulla sain muokattua
muotoilun haluamaani muotoon, jolloin se näytti tältä
![4]
![5]

#### d) Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.

* `git log`

log-komento näyttää repoon tehdyt muutokset/commitit. Muutoslokista selviää jokaisen muutoksen token, muutoksen tehnyt henkilö (author),
muutoksen tarkka aika (date) sekä muutoksentekijän jättämä kommentti muutoksesta (esim. "Raportointia")
![6]

* `git diff`

diff-komennolla voidaan verrata miten ja missä tiedostoissa on eroja githubissa oleviin tiedostoihin verrattuna.
![7]
Esimerkiksi en commitannut vielä viimeisimpiä muutoksia raporttiin, jolloin diff-komento näytti nämä eroavat rivit + -merkillä.

* `git blame`

blame-komennolla selviää, kuka on kirjoittany minkäkin rivin kustakin tiedostosta. Esimerkiksi ajamalla komennon `git blame harjoitus3.md` 
terminaalissa näkyy kyseisen tiedoston jokainen rivi numeroituna, sen sisältö, kirjoittaja ja aikaleima.
![8]

#### e) Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset –hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

Kirjoitin raportin tiedostoon "TYHMÄ MUUTOS" ja tallensin tiedoston.
![9]
Tämän jäleen ajoin komennon `git reset --hard`, joka antoi seuraavan ilmoituksen
![10]
Eli muutokset oltiin muutettu takaisin viimeisimpään committiin.

#### f) Tee uusi salt-moduli. Voit asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman. Käytä tarvittaessa ‘find -printf “%T+ %p\n”|sort’ löytääksesi uudet asetustiedostot. (Tietysti eri ohjelma kuin aiemmissa tehtävissä, tarkoitushan on harjoitella Salttia)

Päätin tehdä moduulin, joka asentaa Kritan. Aloitin luomalla Krita-kansion komennolla `sudo mkdir /srv/salt/krita/`, jonka sisälle loin vielä init.sls -tiedoston komennolla `sudoedit /srv/salt/krita/init.sls`. Tiedoston sisällöksi kirjoitin seuraavan
![11]
Jonka jälkeen ajoin moduulin komennolla `sudo salt '*' state.apply krita`, sain vastaukseksi toiminnon onnistuneen
![12]
Ajoin saman komennon kuitenkin uudestaan varmistaakseni, että se oli idempotentti.
![13]
Vastaukseksi sain sen, että komento onnistui (mutta mitään ei muutettu). Eli moduuli oli idempotentti.
Tarkistin vielä ohjelman varmasti asentuneen hakemalla sitä käynnistys-valikosta ja löysinkin ohjelman myös sieltä.
![14]

[1]: https://i.imgur.com/oO3menW
[2]: https://i.imgur.com/mkj9XqB
[3]: https://i.imgur.com/myY7IjR
[4]: https://i.imgur.com/ZJIr09P
[5]: https://i.imgur.com/VxrfteK
[6]: https://i.imgur.com/tNnqEtF
[7]: https://i.imgur.com/T6xjfR4
[8]: https://i.imgur.com/cCAEnMW
[9]: https://i.imgur.com/9X3SFd3
[10]: https://i.imgur.com/W8K58sJ
[11]: https://i.imgur.com/jOL5kYQ
[12]: https://i.imgur.com/doCz4ir
[13]: https://i.imgur.com/GDqrsn4
[14]: https://i.imgur.com/qBROrxs
