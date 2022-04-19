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
```  
  
Kammottava virhe korjattu.  


## d) Formula. Tee uusi salt-tila (formula, moduli, infraa koodina). (Eli uusi tiedosto esim. /srv/salt/terontila/init.sls). Voit tehdä ihan yksinkertaisen parin funktion (pkg, file...) tilan, tai edistyneemmin asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman. Käytä tarvittaessa ‘find -printf “%T+ %p\n”|sort’ löytääksesi uudet asetustiedostot.

## f) Vapaaehtoinen: Laita srv/salt/ gittiin. Tee uusi moduli. Kloonaa varastosi toiselle koneelle (tai poista srv/salt ja palauta se kloonaamalla) ja jatka sillä.

## e) Vapaaehtoinen: Omaa koiranruokaa. Säädä jotain käyttämääsi konetta Saltilla.