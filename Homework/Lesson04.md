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

The trimmed output after running the state:  

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

Sample timeline from my VirtualBox computer:  
```
$ sudo find /etc/ -printf '%T+ %p\n'|sort|tail
2022-05-01+12:56:31.9640005630 /etc/xdg/autostart/vboxclient.desktop
2022-05-01+12:56:31.9760005630 /etc/X11/Xsession.d/98vboxadd-xclient
2022-05-01+13:04:25.6762335250 /etc/cups/subscriptions.conf.O
2022-05-01+13:05:56.2575050450 /etc/chromium.d
2022-05-01+13:05:56.2655090460 /etc/chromium
2022-05-01+13:05:56.8778150680 /etc/ld.so.cache
2022-05-01+13:05:58.2665091200 /etc/
2022-05-01+13:05:58.2665091200 /etc/mailcap
2022-05-01+14:02:45.1172157060 /etc/cups/subscriptions.conf
2022-05-01+14:02:45.1292217070 /etc/cups
``` 

Command in pieces:  
Piece | Explanation
---|---
sudo | superuser do. Comman is run with the highest privileges in the system. Many locations in /etc/ directory are not available to regular users.
find | Command line application for searching information on files and folders. 
/etc/ | First parameter to find for limiting the search to specific location(s). System's configuration files are located in /etc/ so if one needs to edit or look at certain software text-based config files, this is where to start. User-based settings are at /home/user.  
-printf | Formatted print. User can define the format of the printed output in a string argument following printf.  
' | Beginning of user string argument
%T+ | % starts a directive. It tells the printf command that the user wants to use a preprogrammed feature of printf. In this case it would T as in Time in 24h format with the + denoting that the output should be in Date and time separated by + (year-month-day+hours:minutes:seconds). So this part will format the output string to start with a date and time of the last edit on the found file.
%p | The file name and path that find has found
\n | Newline escape. printf doesn't automatically create new lines, so this is needed for readability
' | End of user string argument
\| |  Pipeline. Give the previews function's/commands output to the next function as a parameter
sort | Sort the output. Unless specified with arguments the sorting is alphabetical. The earlier specified %T+ is important for the sorting to actually work.
tail | Print the tail or the end of the output. If not specified by other arguments, prints the last 10 lines.  
  
So to summarize the issued command prints the last ten edited system configuration files in chronological order with editing timestamps and file paths.  

As an example I opened up the port 22 on my firewall:  
```
$ sudo ufw allow 22
Rule added
Rule added (v6)
pajazzo@derpMaster:$ sudo find /etc/ -printf '%T+ %p\n'|sort|tail
2022-05-01+13:04:25.6762335250 /etc/cups/subscriptions.conf.O
2022-05-01+13:05:56.2575050450 /etc/chromium.d
2022-05-01+13:05:56.2655090460 /etc/chromium
2022-05-01+13:05:56.8778150680 /etc/ld.so.cache
2022-05-01+13:05:58.2665091200 /etc/
2022-05-01+13:05:58.2665091200 /etc/mailcap
2022-05-01+14:02:45.1172157060 /etc/cups/subscriptions.conf
2022-05-01+14:02:45.1292217070 /etc/cups
2022-05-01+14:41:00.7031304050 /etc/ufw/user.rules
2022-05-01+14:41:00.7111304050 /etc/ufw/user6.rules
``` 

As we can see, this single edit changed two different files from the ufw configuration folder. 
This is the line added to both files (with minor differences):  
``` 
### tuple ### allow any 22 0.0.0.0/0 any 0.0.0.0/0 in
-A ufw-user-input -p tcp --dport 22 -j ACCEPT
-A ufw-user-input -p udp --dport 22 -j ACCEPT

$ sudo ufw deny 22
Rule updated
Rule updated (v6)  
```

## c) Tiedän mitä teit viime kesän^H^H^H komennolla. Säädä jotain ohjelmaa ja etsi sen muuttamat tiedostot aikajanasta. Tee sitten tästä oma Saltin tila.

Vinkki: tässä kohdassa pitää muuttaa jonkin ohjelman asetuksia, pelkkä ohjelman asennus pkg.installed on liian helppoa.
 
I will do something else as I've already configured app-specific settings utilizing the find command for VLC and micro during lecture, and for ufw in last weeks homework.  
Let's try to configure Firefox browser to force installation of an adblocker (uBlock).  
According to mozilla's policy-template github repository (https://github.com/mozilla/policy-templates/blob/master/README.md), the location for the user policies should be in a folder firefox/distribution where the distribution folder doesn't necessarily exist and has to be created. For system-wide policy the location is /etc/firefox/policies. I will go for the system-wide settings.  
The policies are specified in a file policies.json and should be cross-platform compatible. 
First I tried setting a simple policy manually via ssh connection to the minion: 
```
$ sudo mkdit /etc/firefox
$ sudo mkdir /etc/firefox/policies
$ sudo micro /etc/firefox/policies.json
$ cat /etc/firefox/policies.json
{
	"policies": {
  		"BlockAboutConfig": true
  	}
}
``` 
According to Mozillas guide (https://support.mozilla.org/en-US/kb/customizing-firefox-using-policiesjson) this should block the user from accessing the about:config page on firefox.

I tried and it did indeed work:

<img src="Homework/Screenshots/Lesson04cconfigBlock.png">

So I added the following to see if I can get the extension to autoinstall:  
```
{
	"policies": {
  		"BlockAboutConfig": true,
  		"ExtensionSettings": {
  			"uBlock0@raymondhill.net": {
  				"installation_mode": "force_installed",
  			 	"install_url": "https://addons.mozilla.org/firefox/downloads/latest/ublock-origin/latest.xpi"
  			 	}
  		}
  	}
}
```

The uBlock0@raymondhill.net is the Extension ID which can be found from about:support page's extension part on the browser. The install_url is in the same place.    
And after this, uBlock was installed automatically to FireFox:

<img src="Homework/Screenshots/Lesson04cublockinstall.png">

Now that the setup was working. I needed to create a salt state for FireFox management.

So the to-do list is to create a salt -state that:  
- checks the installation of Firefox and if needed installs it.  
- creates a folder and parents to /etc/firefox/policies.  
    - For me the /etc/firefox didn't exist as Firefox configuration is in /etc/firefox-esr but Firefox doesn't apparently read the policies from there. Have to do some tests still to see if true.  
- copies a default-policies.json as policies.json file from the salt-master to the aforementioned location on the minion.    

```
$ pwd
/srv/salt
$ sudo mkdir firefox
$ sudo mkdir firefox/files
$ sudo touch firefox/init.sls
$ sudo cp /home/pajazzo/policies.json /srv/salt/firefox/files/default_policies.json
$ cat firefox/files/default_policies.json 
{
	"policies": {
  		"BlockAboutConfig": true,
  		"ExtensionSettings": {
  			"uBlock0@raymondhill.net": {
  				"installation_mode": "force_installed",
  			 	"install_url": "https://addons.mozilla.org/firefox/downloads/latest/ublock-origin/latest.xpi"
  			 	}
  		}
  	}
}
$ sudo micro firefox/init.sls 
$ cat firefox/init.sls 
firefox-esr:
  pkg.installed
/etc/firefox/policies/policies.json:
  file.managed:
    - source: salt://firefox/files/default_policies.json
    - makedirs: True
$ sudo salt 'numberone' state.apply firefox
Summary for numberone
------------
Succeeded: 2
Failed:    0
------------
```  

## d) Asenna jokin toinen ohjelma asetuksineen.

Vinkki: tässäkin kohdassa edellytetään asetusten muuttamista. Jos haluat, voit valita erilaisen ohjelman kuin c-kohdassa. Esimerkiksi jos asensit c-kohdassa demonin, voit asentaa tässä komentoriviohjelman tai graafisen käyttöliittymän ohjelman.
