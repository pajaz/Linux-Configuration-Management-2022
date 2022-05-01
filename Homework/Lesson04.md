# h4 Aikajana

Part of Linux Configuration Management ICT4TN022-3015 course of Haaga-Helia University of Applied Sciences held by Tero Karvinen. Course is in Finnish.  

Course page: https://terokarvinen.com/2021/configuration-management-systems-2022-spring/  

Vinkkejä:

    Lähes kaiken voi konfiguroida viidellä funktiolla: pkg-file-service (watch), user, exec.
    Asenna aina ensin käsin
    Ohjelmat tallentavat asetukset tiedostoihin. Joten aikajana tiedostoista näyttää, mitkä tiedostot pitää tehdä.
    Saltilla asennetaan ohjelma (pkg), laitetaan asetustiedostot paikalleen (file) ja lopuksi jokin ohjelma lukee tiedot (service-watch; työpöytäohjelma kun se avataan; pakettilista sudo apt-get update tai pkg-refresh).
    Testaa. Tee pienin testattava kokonaisuus kerralla.

## a) Captain obvious. Linuxissa on paketinhallinta, joten ohjelmien asentaminen on yksinkertaista. Tee tila, joka asentaa 10 suosikkiohjelmaasi paketinhallinnasta. Tässä a-kohdassa voit jättää ohjelmat oletusasetuksille.

List of applications and commands for installation:  
- Mozilla Firefox browser  
    * apt-get install firefox-esr  
- Micro text editor  
    * apt-get install micro  
- Gedit for text-editing requiring more complex features (Still a very barebones application) 
    * apt-get install gedit  
- Flameshot screenshot tool  
    * apt-get install flameshot  
- bash-completion for auto completion of command-line commands  
    * apt-get install bash-completion
- VLC-media player  
    * apt-get install vlc
- KeepassXC password manager  
    * apt-get install keepassxc  
- git for distributed version control  
    * apt-get install git  

I created a new directory for the state and the initiation file with just one test package for now:  
```
$ sudo mkdir /srv/salt/commonpkg-set
$ cd /srv/salt/commonpkg-set
$ micro init.sls
commonpkg-set:
  pkg.installed:
    - pkgs:
      - flameshot
```

And then ran the state for my test minion:  
```
$ sudo salt 'numberone' state.apply commonpkg-set
numberone:
----------
          ID: commonpkg-set
    Function: pkg.installed
      Result: True
     Comment: The following packages were installed/updated: flameshot
     Started: 13:36:13.043199
    Duration: 5172.101 ms
     Changes:   
Summary for numberone
------------
Succeeded: 1 (changed=1)
Failed:    0
------------
```
The output shows that the state commonpkg-set containing the function pkg.installed was run succesfully with one change made.  

I continued to add the rest of the needed packages in to the init.sls file:  
```
commonpkg-set:
  pkg.installed:
    - pkgs:
      - flameshot
      - firefox-esr
      - micro
      - gedit
      - bash-completion
      - vlc
      - keepassxc
      - git
```

The trimmed output:  

```
$ sudo salt 'numberone' state.apply commonpkg-set
numberone:
----------
          ID: commonpkg-set
    Function: pkg.installed
      Result: True
     Comment: The following packages were installed/updated: vlc, keepassxc, git
              The following packages were already installed: flameshot, firefox-esr, micro, gedit, bash-completion
     Started: 13:49:07.327572
    Duration: 32913.18 ms
Summary for numberone
------------
Succeeded: 1 (changed=1)
Failed:    0
------------
Total states run:     1
Total run time:  32.913 s
```

As we can see the state works as intended. Most pkgs were already installed on the target system and the rest are now installed.  

Vinkkejä: Asenna tässä a-kohdassa valmiiksi luotetuista pakettivarastoista, niin ei tarvitse asentaa uusia varastoja, ja tiedät saavasi vapaita ohjelmia. Ohjelmien asennus voi viedä aikaa, jos haluat seurata etenemistä komento komennolta niin 'sudo salt-call --local -l debug state.apply terosapps'. Sisäänrakennettu ohje kertoo, kuinka "pgks" toimii: 'salt-call --local sys.state_doc pkg.installed|less'

## b) CSI Pasila. Tiedostoista saa aikajanan 'cd /etc/; sudo find -printf '%T+ %p\n'|sort|tail'.

    Anna esimerkki aikajanasta
    Selitä jokainen kohta komennosta, jolla aikajana tehdään. Vinkki: '%T+' löytyy 'man find' kohdasta printf.
    Aja jokin komento, joka muuttaa järjestelmän yhteisiä asetustiedostoja
    Ota uusi aikajana ja etsi muutos sieltä
    Onko samalla hetkellä muutettu yhtä vai useampaa tiedostoa?

## c) Tiedän mitä teit viime kesän^H^H^H komennolla. Säädä jotain ohjelmaa ja etsi sen muuttamat tiedostot aikajanasta. Tee sitten tästä oma Saltin tila.

Vinkki: tässä kohdassa pitää muuttaa jonkin ohjelman asetuksia, pelkkä ohjelman asennus pkg.installed on liian helppoa.

## d) Asenna jokin toinen ohjelma asetuksineen.

Vinkki: tässäkin kohdassa edellytetään asetusten muuttamista. Jos haluat, voit valita erilaisen ohjelman kuin c-kohdassa. Esimerkiksi jos asensit c-kohdassa demonin, voit asentaa tässä komentoriviohjelman tai graafisen käyttöliittymän ohjelman.
