# h3 Versionhallinta

Part of Linux Configuration Management ICT4TN022-3015 course of Haaga-Helia University of Applied Sciences held by Tero Karvinen. Course is in Finnish.  

Course page: https://terokarvinen.com/2021/configuration-management-systems-2022-spring/  
 
## z) Lue ja tiivistä artikkeli muutamalla ranskalaisella viivalla. Tässä z-alakohdassa ei tarvitse siis tehdä testejä tietokoneella.

* Commonmark contributors: Markdown Reference (huomaa ainakin otsikot risuaidoilla, kappalejako tyhjällä rivillä, sisennys (tab) koodia, lista, linkki, kuva.

## a) MarkDown. Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän.  

(Linkki tämän dokumentin raakaversioon)[https://raw.githubusercontent.com/pajaz/Linux-Configuration-Management-2022/main/Homework/Lesson03.md]
  
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


## c) Huppis! Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset --hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

## d) Formula. Tee uusi salt-tila (formula, moduli, infraa koodina). (Eli uusi tiedosto esim. /srv/salt/terontila/init.sls). Voit tehdä ihan yksinkertaisen parin funktion (pkg, file...) tilan, tai edistyneemmin asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman. Käytä tarvittaessa ‘find -printf “%T+ %p\n”|sort’ löytääksesi uudet asetustiedostot.

## f) Vapaaehtoinen: Laita srv/salt/ gittiin. Tee uusi moduli. Kloonaa varastosi toiselle koneelle (tai poista srv/salt ja palauta se kloonaamalla) ja jatka sillä.

## e) Vapaaehtoinen: Omaa koiranruokaa. Säädä jotain käyttämääsi konetta Saltilla.