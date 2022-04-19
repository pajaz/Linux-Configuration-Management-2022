# h3 Versionhallinta

Part of Linux Configuration Management ICT4TN022-3015 course of Haaga-Helia University of Applied Sciences held by Tero Karvinen. Course is in Finnish.  

Course page: https://terokarvinen.com/2021/configuration-management-systems-2022-spring/  
 
## z) Lue ja tiivistä artikkeli muutamalla ranskalaisella viivalla. Tässä z-alakohdassa ei tarvitse siis tehdä testejä tietokoneella.

* Commonmark contributors: Markdown Reference (huomaa ainakin otsikot risuaidoilla, kappalejako tyhjällä rivillä, sisennys (tab) koodia, lista, linkki, kuva.

## a) MarkDown. Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän.  

[Linkki tämän dokumentin raakaversioon](https://raw.githubusercontent.com/pajaz/Linux-Configuration-Management-2022/main/Homework/Lesson03.md)
  
## b) Pull first. Tee useita muutoksia git-varastoosi. Tee muutama muutos, jossa yksi commit koskee useampaa tiedostoa. Anna hyvä kuvaukset (commit message), yksi englanninkielinen lause imperatiivissa (määräysmuodossa) "Add top level menu to Foobar synchronizer"
  
    $ git pull
    $ ## Tässä välissä tein muutokset repositorioon. 
    $ git commit -a -m "Add Lesson 3 assignments to Lesson03.md and lesson 3 link to README.md"
    $ git push

Komento | Selitys  
---|---
pull | Ladataan etärepositorio eli tässä tapauksessa Githubissa oleva repositoria koneelle, jotta paikallinen kopio on varmasti samassa tilassa uusimman julkaistun version kanssa.  
commit | Asetetaan tehdyt muutokset julkaistavaksi, muttei vielä tehdä muuta. -a vipu lisää kaikkiin tiedostoihin tehdyt muutokset julkaisuun. -m lisää saman kommentin kaikkiin tiedostoihin.  
push | Työnnetään muutokset onlinerepositorioon.  
  
## b) Kaikki kirjataan. Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.  

```
pajazzo@derpface:$ git log
commit 256d9153901553a115be44535ad7b9fe92c00f67 (HEAD -> main, origin/main, orig
in/HEAD)
Author: pajaz <mikko.pajunen@myy.haaga-helia.fi>
Date:   Tue Apr 19 10:58:47 2022 +0300

    Add Lesson 3 assignments to Lesson03.md and lesson 3 link to README.md

commit 2a51d5108edda7834ebe8c3c6f5e1732eb01250c
Author: pajaz <mikko.pajunen@myy.haaga-helia.fi>
Date:   Wed Apr 13 18:54:23 2022 +0300

    add Lesson03.md
```
log -komento näyttää git commit historian. Se pitää sisällään commitin yksilöidyn tunnuksen, jonka avulla voidaan mm. palauttaa repositorio kyseisen commitin aikaiseen tilaan. Perässä on suluissa oleva pätkä tarkoittaa, että paikallisen kopion HEAD eli tämänhetkinen tila yhdistetään main -branchiin. Komento ilmoittaa myös commitin tekijän (Author) ja ajankohdan (Date), sekä committiin annetun kommentin.  
  
```
pajazzo@derpface:$ git diff
diff --git a/Homework/Lesson03.md b/Homework/Lesson03.md
index a67a315..1188d24 100644
--- a/Homework/Lesson03.md
+++ b/Homework/Lesson03.md
@@ -14,10 +14,35 @@ Course page: https://terokarvinen.com/2021/configuration-management-systems-2022
   
 ## b) Pull first. Tee useita muutoksia git-varastoosi. Tee muutama muutos, jossa yksi commit koskee useampaa tiedostoa. Anna hyvä kuvaukset (commit message), yksi englanninkielinen lause imperatiivissa (määräysmuodossa) "Add top level menu to Foobar synchronizer"
   
+    $ git pull
+    $ ## Tässä välissä tein muutokset repositorioon. 
+    $ git commit -a -m "Add Lesson 3 assignments to Lesson03.md and lesson 3 link to README.md"
+    $ git push
+
+Komento | Selitys  
+---|---
+pull | Ladataan etärepositorio eli tässä tapauksessa Githubissa oleva repositoria koneelle, jotta paikallinen kopio on varmasti samassa tilassa uusimman julkaistun version kanssa.  
+commit | Asetetaan tehdyt muutokset julkaistavaksi, muttei vielä tehdä muuta. -a vipu lisää kaikkiin tiedostoihin tehdyt muutokset julkaisuun. -m lisää saman kommentin kaikkiin tiedostoihin.  
+push | Työnnetään muutokset onlinerepositorioon.  
   
+## b) Kaikki kirjataan. Näytä omalla git-varastollasi esimerkit komennoista ‘gi
+Komento | Selitys  
+---|---
+pull | Ladataan etärepositorio eli tässä tapauksessa Githubissa oleva repositor
ia koneelle, jotta paikallinen kopio on varmasti samassa tilassa uusimman julkai
stun version kanssa.  
+commit | Asetetaan tehdyt muutokset julkaistavaksi, muttei vielä tehdä muuta. -
a vipu lisää kaikkiin tiedostoihin tehdyt muutokset julkaisuun. -m lisää saman k
ommentin kaikkiin tiedostoihin.  
+push | Työnnetään muutokset onlinerepositorioon.  
   
+## b) Kaikki kirjataan. Näytä omalla git-varastollasi esimerkit komennoista ‘gi
t log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.  
 
+```
+pajazzo@derpface:$ git log
+commit 256d9153901553a115be44535ad7b9fe92c00f67 (HEAD -> main, origin/main, orig
+in/HEAD)
+Author: pajaz <mikko.pajunen@myy.haaga-helia.fi>
+Date:   Tue Apr 19 10:58:47 2022 +0300
+
+    Add Lesson 3 assignments to Lesson03.md and lesson 3 link to README.md
+
+commit 2a51d5108edda7834ebe8c3c6f5e1732eb01250c
+Author: pajaz <mikko.pajunen@myy.haaga-helia.fi>
+Date:   Wed Apr 13 18:54:23 2022 +0300
+
+    add Lesson03.md
+```
 
-## b) Kaikki kirjataan. Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.

 ## c) Huppis! Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset --hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.
```
  
diff -komento ilmoittaa tiedostoittain edellisen commitin jälkeen tehdyt muutokset. Vihreät plusmerkkiset rivit ovat lisäyksiä, Punaiset miinusmerkkiset poistoja ja harmaisiin merkkaamattomiin riveihin ei ole tehty muutoksia.  
Lähde: https://www.geeksforgeeks.org/git-diff/  
  
```
pajazzo@derpface:$ git blame Homework/Lesson03.md
## Palauteesta otettu vain kaksi esimerkkiä tilan säästämiseksi.
256d9153 (pajaz             2022-04-19 10:58:47 +0300  1) # h3 Versionhallinta
2a51d510 (pajaz             2022-04-13 18:54:23 +0300  3) Part of Linux Configuration Management ICT4TN022-3015 course of Haaga-Helia University of Applied Sciences held by Tero Karvinen. Course is in Finnish.  
00000000 (Not Committed Yet 2022-04-19 11:21:43 +0300 31) pajazzo@derpface:$ git log
```
  
blame -komento näyttää tiedostoon tehdyt muutokset riveittäin. Tietue pitää sisällään commitin hash-arvon alkuosan eli missä commitissa kyseistä riviä on viimeksi muokattu, kuka on tehnyt muokkkauksen, muokkauksen ajankohdan, sekä itse rivin.  
  
## c) Huppis! Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset --hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

Poistin koko Homework sijainnin paikallisesta versiostani ja käytin git reset --hard komentoa, joka palautti repositorioini edellisen commitin tilaan, kuten viimeisestä git log -komennosta huomataan:  
```
pajazzo@derpface:$ rm -r Homework/
pajazzo@derpface:$ 
pajazzo@derpface:$ ls
PersonalNotes  README.md
pajazzo@derpface:$ git reset --hard
HEAD is now at 808fb02 Add Lesson03.md assignment b
pajazzo@derpface:$ ls
Homework  PersonalNotes  README.md  
pajazzo@derpface:$ git log
commit 808fb0222a54792dbb3744102fb306740dceef81 (HEAD -> main, origin/main, origin/HEAD)
Author: pajaz <mikko.pajunen@myy.haaga-helia.fi>
Date:   Tue Apr 19 11:28:46 2022 +0300
```
   
Tein vielä vähän vakavampia muutoksia testitiedostolla. Loin tiedoston testfile ja siihen jotakin tekstiä. minkä jälkeen commit ja push:  
```
## Syötteestä karsittu turha palaute
pajazzo@derpface:$ micro testfile
pajazzo@derpface:$ cat testfile 
Tämä on testiä
pajazzo@derpface:$ git add testfile 
pajazzo@derpface:$ git commit -a -m "Add testfile for hard reset demonstration"
pajazzo@derpface:$ git push
```

Testasin hard resettiä ja huomasin, ettei se tee oikeastaan mitään nyt, kun edellinen commit on sama joka pitäisi perua:  
```
pajazzo@derpface:$ ls
Homework  PersonalNotes  README.md  testfile
pajazzo@derpface:$ git reset --hard
HEAD is now at 63a8f53 Add testfile for hard reset demonstration  
```
  
Vilkaisin git resetin manuaalia, josta löytyi tarvittava syntaksi tilanteen palauttamiseksi haluttuun committiin:  
```
pajazzo@derpface:$ git reset --help
## 
git reset [--soft | --mixed [-N] | --hard | --merge | --keep] [-q] [<commit>]
##
pajazzo@derpface:$ git log
commit 63a8f531db7c8b4796b6e61deaa11898773779b2 (HEAD -> main, origin/main, origin/HEAD)
Author: pajaz <mikko.pajunen@myy.haaga-helia.fi>
Date:   Tue Apr 19 11:43:51 2022 +0300

    Add testfile for hard reset demonstration

commit 808fb0222a54792dbb3744102fb306740dceef81     ## Tähän halutaan palata
Author: pajaz <mikko.pajunen@myy.haaga-helia.fi>
Date:   Tue Apr 19 11:28:46 2022 +0300

    Add Lesson03.md assignment b
```
  
Ajoin tarvittavan komennon:  
```
pajazzo@derpface:$ git reset --hard 808fb0222a54792dbb3744102fb306740dceef81
HEAD is now at 808fb02 Add Lesson03.md assignment b
pajazzo@derpface:$ ls
Homework  PersonalNotes  README.md
pajazzo@derpface:$ git log
commit 808fb0222a54792dbb3744102fb306740dceef81 (HEAD -> main)
Author: pajaz <mikko.pajunen@myy.haaga-helia.fi>
Date:   Tue Apr 19 11:28:46 2022 +0300

    Add Lesson03.md assignment b
```  
  
git log -komennon ajosta huomataan, että virheellinen commit on poistunut kokonaan lokihistoriasta ja virhe siis korjattu. Kuitenkin kyseinen tiedosto on edelleen olemassa remote repositoriossa ja git status ilmoittaa, että paikallinen repositorioini on yhden commitin jäljessä:  
```
pajazzo@derpface:$ git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
```
  
Jos nyt tekisin ehdotetun pullin, päätyisi tuo testitiedosto takaisin koneelleni. Loin tässä vaiheessa uuden branchin nimeltä newmain, otin sen käyttöön checkout komennolla ja tein commitin ja pushin. Halusin tämän newmain branchin myös etärepositoriooni, jos vaikka vahingossa onnistuisin tekemään pahempia virheitä, niin ainakin kaikki on tallessa pilvessä.   
Tämän jälkeen vaihdoin takaisin main -branchiini, resetoin main branchin samaan pisteeseen kuin newmain, tein commitin ja push-f eli push force vivun kanssa. Tässä välissä tuli tehtyä paljon testailua eri vaiheilla, joten muutamia ylimääräisiä committeja tuli tehtyä joita ei tässä kohdassa näy. Jos teet töitä muiden kanssa, älä käytä -f vipua pushin kanssa kevyin perustein, koska se pakottaa sinun muutoksesi branchiin.    
``` 
pajazzo@derpface:$ git branch newmain
pajazzo@derpface:$ git checkout newmain
Switched to branch 'newmain'
pajazzo@derpface:$ git commit -a -m "newmain for merge"
On branch newmain
nothing to commit, working tree clean
pajazzo@derpface:$ git push --set-upstream origin newmain
pajazzo@derpface:$ git checkout main
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)
pajazzo@derpface:$ git reset --hard newmain 
HEAD is now at 5830d17 testfiles removed
pajazzo@derpface:$ git push -f origin main
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:pajaz/Linux-Configuration-Management-2022.git
 + c5afb02...5830d17 main -> main (forced update)
```  
  
Tämä aiheutti paljon merge konflikteja tiedostoon Lesson03.md jotka kävin ratkaisemassa paikallisesti. Visual Studio Codesta voidaan olla montaa mieltä, mutta konfliktien ratkaisu on siinä helppoa tähän tarkoitukseen luodun näkymän kautta. Kun konfliktit oli ratkaistu paikallisesti, tein normaalisti commitin ja pushin. Repositorioni on taas ajan tasalla.  

Lopputulemana sanoisin, että git reset --hard komentoa ei kannata käyttää kevyin perustein ainakaan perumaan jo etärepositorioon pushattuja muutoksia, koska tämä aiheuttaa helposti ongelmia. Hard resetillä voi myös helposti vahingossa pyyhkiä commit -historiansa pois.      

git reset --help komennon kautta selviää myös, että palautukseen voi käyttää commitin tunnuksen sijasta HEAD~x (x=1...n) parametria, joka palauttaa repositorion x:n verran taaksepäin commit historiassa. Erikoistapauksena, jos halutaan perua vain edellinen commit voidaan käyttää HEAD^ -parametria.  
  
## d) Formula. Tee uusi salt-tila (formula, moduli, infraa koodina). (Eli uusi tiedosto esim. /srv/salt/terontila/init.sls). Voit tehdä ihan yksinkertaisen parin funktion (pkg, file...) tilan, tai edistyneemmin asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman. Käytä tarvittaessa ‘find -printf “%T+ %p\n”|sort’ löytääksesi uudet asetustiedostot.
  
Päätin asentaa Minion -koneelleni 'numberone' palomuurin.  
  
1. Manuaalinen asennus.  
  
    $ sudo apt-get install ufw
    $ sudo ufw enable
    $ ## palvelimen uudelleenkäynnistys
    $ sudo ufw status
    $ sudo systemctl status ufw.service

Molemmat status-checkit ilmoittivat palomuurin olevan päällä.  
  
2. Manuaalinen porttien avaus ja ssh-yhteyden testaus.    
  
Edellisellä viikolla asetin minion koneen ssh -palvelimen toimimaan portin 7373 kautta. Koska koneelle on asennettuna palomuuri, piti kyseinen portti avata käyttöön, jotta ssh -yhteys koneelle onnistuu ulkopuolelta.  
  
    $ sudo ufw allow 7373/tcp  

Masterilla testaus: 
  
    $ pajazzo@derpMaster:$ ssh pajazzo@192.168.1.8 -p 7373
    $ pajazzo@derpSlave1:$ 
  
Yhteys toimi hyvin.  
  
3. Salt asennus.  
  
Loin /srv/salt sijaintiin ufw:lle oman sijantinsa ja sinne init.sls tiedoston johon laitoin aluksi vain paketin asennuksen ja palvelun käynnistämisen testauksen:  
```
pajazzo@derpMaster:$ sudo mkdir /srv/salt/ufw/
pajazzo@derpMaster:$ cd /src/salt/ufw/
pajazzo@derpMaster:$ micro init.sls
pajazzo@derpMaster:$ cat init.sls 
ufw:
  pkg.installed
ufw.service:
  service.running:
    - name: ufw
pajazzo@derpMaster:$ sudo salt 'numberone' state.apply ufw
### Molempien tilojen ajo onnistui, paketti oli jo asennettu ja palvelu käynnissä, joten muutoksia ei tehty
```

Asennus onnistui joten siirryin konfiguraatiovaiheeseen.    
  
4. Salt konfiguraatiohallinta.
  
Tässä kohdassa jouduin vähän tutkimaan ufw:n konfiguraatiokansiota /etc/ufw/ löytääkseni, mikä/mitkä tiedostot pitävät sisällään halutut asetukset.  
Loogisesti ajattelin, että tiedosto ufw.conf olisi tärkeä tähän. Kyseinen tiedosto pitääkin sisällään palomuurin palvelun käynnistämiseen tietokoneen käynnistämisen yhteydessä tarvittavan rivin, sekä palomuurin lokitason määrityksen. Hyödyllinen tiedosto eli otetaan talteen.  
user.config ja user6.config tiedostot tuntuivat pitävän sisällään tehdyt porttien avaustiedot riveillä (**Huom.** rivit eivät ole täysin samanlaiset molemmissa user* tiedostoissa):  
  
    $ ### tuple ### allow tcp 7373 ::/0 any ::/0 in
    $ -A ufw6-user-input -p tcp --dport 7373 -j ACCEPT
  
Loput /etc/ufw ja etc/ufw/applications.d/ tiedostoista eivät pitäneet sisällään näihin asetuksiin liittyviä tietueita. Tosin applications.d sijainnissa oleva openssh-server asetustiedosto määrittää portiksi 22 eli saman joka viime viikolla vaihdettiin porttiin 7373. Tämä kansio pitää oman ymmärrykseni mukaan sisällään sovellusten omia ufw -asetustiedostoja, jotka voidaan ajaa komennolla `sudo ufw allow *tiedoston_nimi*` eli tässä vaiheessa näistä ei tarvitse välittää.  
  
Tarpeelliset tiedostot siis, kopion näiden sisällöt erilliseen tiedostoon masterille:  
/etc/ufw/ufw.conf  
/etc/ufw/user.rules   
/etc/ufw/user6.rules  
   
Seuraavaksi loin saltin ufw -sijaintiin tiedostoille oman kansion ja tarvittavien tiedostojen default-versiot:  
  
```
pajazzo@derpMaster:$ sudo mkdir /srv/salt/ufw/files
pajazzo@derpMaster:$ cd /srv/salt/ufw/files/
pajazzo@derpMaster:$ sudo micro /srv/salt/ufw/files/user.rules-default
pajazzo@derpMaster:$ sudo micro /srv/salt/ufw/files/user6.rules-default
pajazzo@derpMaster:$ sudo micro /srv/salt/ufw/files/ufw.conf-default
## Tiedostojen sisällöiksi minion -koneelta kopioidun vastaavan tiedoston sisältö. 
pajazzo@derpMaster:$ ls
ufw.conf-default  user6.rules-default  user.rules-default
``` 
  
Muokkasin tiedostot saltin ufw:n init.sls hallintaan:  
```
pajazzo@derpMaster:$ sudo micro init.sls 
ufw:
  pkg.installed
ufw.service:
  service.running:
    - name: ufw
    - watch:
      - file: /etc/ufw/ufw.conf
      - file: /etc/ufw/user.rules
      - file: /etc/ufw/user6.rules
/etc/ufw/ufw.conf:
  file.managed:
    - source: salt://ufw/files/ufw.conf-default
/etc/ufw/user.rules:
  file.managed:
    - source: salt://ufw/files/user.rules-default
/etc/ufw/user6.rules:
  file.managed:
    - source: salt://ufw/files/user6.rules-default 
```
  
Testasin jälleen ajaa tilat ja kaikki palautui onnistuneena ilman, että muutoksia tarvitsi tehdä.  
Seuraavaksi poistin Minion -koneelta ufw:n kokonaan ja testasin tilojen ajamista:  
```
pajazzo@derpSlave1:$ sudo apt-get purge ufw
[sudo] password for pajazzo: 
pajazzo@derpSlave1:$ sudo systemctl stop ufw
pajazzo@derpSlave1:$ sudo rm -r /etc/ufw 
pajazzo@derpSlave1:$ exit
pajazzo@derpMaster:$ sudo salt 'numberone' state.apply ufw
## Kaikki 5 tilaa ajettu onnistuneesti ja tehty 5 muutosta
```
  
Tämän jälkeen yritin ottaa ssh -yhteyden Minionille, mutta tämä ei onnistunutkaan enää. Komentorivi jäi vain välkyttämään tyhjää.  
Avasin Minion koneen, ja tarkistin ufw:n tilan komennolla `ufw status`, joka vaikutti kyllä olevan päällä.  
Ajoin tämän jälkeen komennon `ufw reload`, mikä päätyi iptables virheeseen, jonka onnistuin kadottamaan ja ongelmaan lukiessa tiedostoa user.rules.  
Ajoin vielä komennon `ufw enable` ja sain palautteen: 
  
    $ pajazzo@derpSlave1:$ sudo ufw enable
    $ Firewall is active and enabled on system startup
  
Testasin vielä käynnistää koneen uudelleen, minkä jälkeen kaikki lähti toimimaan normaalisti.   
Selvittelin voisiko tästä selvitä eteenpäin ilman järjestelmän uudelleenkäynnistystä. Poistin uudestaan ufw:n, ajoin tilat ja ajoin komennon:  
```    
$pajazzo@derpMaster:$ sudo salt 'numberone' cmd.run 'ufw reload'
numberone:
ERROR: problem running ufw-init
iptables-restore: line 38 failed

Problem running '/etc/ufw/user.rules' ### Tämä oli sama virhe kuin ensimmäisellä yrityksellä
pajazzo@derpMaster:$ sudo salt 'numberone' cmd.run 'ufw enable'
numberone:
    Firewall is active and enabled on system startup
pajazzo@derpMaster:$ sudo salt 'numberone' cmd.run 'ufw reload'
numberone:
    Firewall reloaded ### Huomataan, että virhe poistui, kun ensin ajettiin ufw enable komento.  
```
  
Tämän jälkeen myös yhteys lähti toimimaan koneelle, eli asetukset menivät oikein läpi ilman uudelleenkäynnistystä.  
Pitää vielä testata miten tuon komentojen ajon saisi sisällytettyä asennuksen yhteyteen.  
  
Huomasin, että minulla oli **kirjoitusvirhe** tiedostossa srv/salt/ufw/files/user.rules-default, joka aiheutti ongelmakäyttäytymisen, jonka tuo enable + reload tai reboot yhdistelmä korjasi itsestään. Huomasin ongelman, kun tilojen ajaminen useamman kerran teki aina muutoksia kyseiseen tiedostoon, vaikkei siihen olisi koskettu välissä. Korjattuani virheen default-tiedostoon, alkoivat asetukset toimimaan kuten pitääkin.  
  
## f) Vapaaehtoinen: Laita srv/salt/ gittiin. Tee uusi moduli. Kloonaa varastosi toiselle koneelle (tai poista srv/salt ja palauta se kloonaamalla) ja jatka sillä.

## e) Vapaaehtoinen: Omaa koiranruokaa. Säädä jotain käyttämääsi konetta Saltilla.