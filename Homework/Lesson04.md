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

List of applications:  
- Mozilla Firefox browser  
    * sudo apt install firefox
- Micro text editor  
- Gedit for text-editing requiring more complex features (Still quite simple application) 
- Flameshot screenshot tool  
- Oracle VM VirtualBox hypervizor for Hardware and Software Virtualization    
- bash-completion for auto completion of command-line commands  
- VLC-media player  
- KeepassXC password manager  
- git for distributed version control  



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
