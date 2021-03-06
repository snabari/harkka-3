# Palvelinten Hallinta kevät 2020 harjoitus 3

Käytössäni on Win10 pöytäkone(Ryzen 5 3600, 16Gb 3200mhz, AMD RX 480 8Gb).
Virtualbox ympäristö käytössä jossa on xubuntu 18.04 virtuaalikone.

a) MarkDown. Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän.

d) Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.

e) Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset –hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

f) Tee uusi salt-moduli. Voit asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman. Käytä tarvittaessa ‘find -printf “%T+ %p\n”|sort’ löytääksesi uudet asetustiedostot. (Tietysti eri ohjelma kuin aiemmissa tehtävissä, tarkoitushan on harjoitella Salttia)

# Tehtävä a:
Aloitin tehtävän seuraamalla Tero Karvisen [ohjeita](http://terokarvinen.com/2016/publish-your-project-with-github). Joissa selitettiin miten github otetaan käyttöön.

github.com sivulla voi rekisteröityä ja luoda uuden Repositoryn.

Repositorylle annetaan nimi, valitaan julkiseksi ja valitaan lisenssi "GNU General Public Li9cense v3.0".

Xubuntussa saa gitin asennettua komennolla

*sudo apt-get -y install git*

Kerrotaan gitille sposti ja nimi jotta tiimiläisen näkemät tämän tiedon "git log":ssa. 

Laitetaan myös koneen muistamaan salasanan tunniksi.

*git config --global user.email "mattimeikalainen@example.com"*

*git config --global user.name "Mark Rybin"*

*git config --global credential.helper "cache --timeout=3600"*

Kun repository on luotu painamalla vihreää clone nappia paljaltuu repositoryn osoite minkä avulla saadaan hakemisto omalle koneelle käyttämällä komentoa

*git clone https://github.com/snabari/harkka-3.git*

Komennolla *git add. && git commit; git pull && push* saadaan päivitettyä uusimmat muutokset.

# Tehtävä d:

**Git Log**

Näyttää kaikki repositoryyn ajetut muutokset sekä commitit, sisältö on commit token, committaaja, commitin aika ja päivitetty tiedosto.

**Git Diff**

Näyttää muutokset ja eron paikallisen hakemiston ja reposirotyn välillä.

**Git Blame**

Näyttää kuka käyttäjä on kirjoittanut minkäkin rivin tiedostosta.

# Tehtävä e:

Loin hakemistoon teksti tiedoston ilman committia.

*cat > testi.txt*

*git add testi.txt*

Poistan sen komennolla

*git reset --hard*

# Tehtävä f

Loin kansion komennolla ja siihen sisällön komennoilla

*sudo mkdir /srv/salt/dolphin/*

*cd /srv/salt/dolphin/*

*sudo nano init.sls*

*dolphin-emu:*

  *pkg.installed*
  
Jonka jälkeen tallennetaan sls tiedosto ja ajetaan saltissa

*sudo salt '*' state.apply dolphin*

Hetken päästä dolphin emulaattori oli asennettu koneelle.

# Lähteet

https://guides.github.com/features/mastering-markdown/

https://www.atlassian.com/git/tutorials/saving-changes/git-diff

https://git-scm.com/docs/git-blame

https://docs.saltstack.com/en/master/topics/tutorials/starting_states.html

https://github.com/terokarvinen/sirotin

http://terokarvinen.com/2016/publish-your-project-with-github
