# h1 Hei maailma & monet tilat

## z) Lue ja tiivistä kukin artikkeli muutamalla ranskalaisella viivalla. 
Tässä z-alakohdassa ei tarvitse siis tehdä testejä tietokoneella.  

  - Karvinen 2021: Salt Run Command Locally
  - Karvinen 2018: Salt Quickstart - Salt Stack Master and Slave on Ubuntu
    Linux
  - Karvinen 2017: Vagrant Revisited - Install & Boot New Virtual Machine in 31
    seconds
  - Karvinen 2021: Two Machine Virtual Network With Debian 11 Bullseye and
    Vagrant
  - Karvinen 2020: Command Line Basics Revisited

Tee ja raportoi: Kokeet tulee tehdä tietokoneella ja kirjoittaa raportti
samalla. Vaikka olisit joskus kokeillut samanlaisia asioita, pelkkä muistelu ei
riitä, vaan testit tulee tehdä ja raportoida samalla.

## a) Mikä meininki? Selvitä, mikä käyttöjärjestelmä (Linuxin versio) sinulla on käytössä, ja mikä Saltin versio.  
  
Käytin Linux version selvitykseen komentoa lsb_release ja sen -a (all) optiota. Tuloste on melko itsensäselittävä.   
```
pajazzo@derpMaster:$ lsb_release -a
No LSB modules are available.
Distributor ID:	Debian
Description:	Debian GNU/Linux 11 (bullseye)
Release:	11
Codename:	bullseye
```
  
En ole erikseen asentanut saltia käytössä olevalle virtuaalikoneelleni, joten version tarkistus palautti luonnollisesti virheen:  
```
pajazzo@derpMaster:~$ sudo salt-call --version
sudo: salt-call: command not found
```
  
Asensin salt-minionin ja tarkistin version:  
```  
pajazzo@derpMaster:$ sudo apt-get install salt-minion
pajazzo@derpMaster:$ sudo salt-call --version
salt-call 3002.6
```  
  
Vastaus:  
Käytössä on Linux Debian 11 (bullseye) käyttöjärjestelmä ja asennettuna salt-minion versio 3002.6
  
Lähteet:  
https://terokarvinen.com/2021/salt-run-command-locally/  
man lsb_release  
  
## b) Onko tietoa? Kerää jostain koneesta tiedot Saltilla, esimerkiksi käyttöjärjestelmä, vapaan muistin määrä, virtualisointi jne. Poimi tuloksesta olennaiset osat ja selitä ne.  
     
```
pajazzo@derpMaster:$ sudo salt-call --local grains.items
[sudo] password for pajazzo: 
local:
    ----------
    biosreleasedate:
        12/01/2006
    biosversion:
        VirtualBox
    cpu_flags:
        - fpu
        - vme
        - de
        - pse
        - tsc
        - msr
        - pae
        - mce
        - cx8
        - apic
        - sep
        - mtrr
        - pge
        - mca
        - cmov
        - pat
        - pse36
        - clflush
        - mmx
        - fxsr
        - sse
        - sse2
        - ht
        - syscall
        - nx
        - rdtscp
        - lm
        - constant_tsc
        - rep_good
        - nopl
        - xtopology
        - nonstop_tsc
        - cpuid
        - tsc_known_freq
        - pni
        - pclmulqdq
        - monitor
        - ssse3
        - cx16
        - pcid
        - sse4_1
        - sse4_2
        - x2apic
        - movbe
        - popcnt
        - aes
        - xsave
        - avx
        - rdrand
        - hypervisor
        - lahf_lm
        - abm
        - 3dnowprefetch
        - invpcid_single
        - pti
        - fsgsbase
        - avx2
        - invpcid
        - rdseed
        - clflushopt
        - md_clear
        - flush_l1d
        - arch_capabilities
    cpu_model:
        Intel(R) Core(TM) i5-7300HQ CPU @ 2.50GHz
    cpuarch:
        x86_64
    cwd:
        /home/pajazzo
    disks:
        - sr0
        - sda
    dns:
        ----------
        domain:
        ip4_nameservers:
        ip6_nameservers:
        nameservers:
        options:
        search:
        sortlist:
    domain:
    fqdn:
        derpMaster
    fqdn_ip4:
        - 127.0.1.1
        - 127.0.1.1
        - 127.0.1.1
    fqdn_ip6:
        - fe80::8950:df02:ce9a:5ce0
        - fe80::8950:df02:ce9a:5ce0
        - fe80::8950:df02:ce9a:5ce0
    fqdns:
        - derpMaster
    gid:
        0
    gpus:
        |_
          ----------
          model:
              SVGA II Adapter
          vendor:
              vmware
    groupname:
        root
    host:
        derpMaster
    hwaddr_interfaces:
        ----------
        enp0s3:
            08:00:27:0c:6b:ca
        lo:
            00:00:00:00:00:00
    id:
        derpMaster
    init:
        systemd
    ip4_gw:
        False
    ip4_interfaces:
        ----------
        enp0s3:
            - 192.168.56.6
        lo:
            - 127.0.0.1
    ip6_gw:
        False
    ip6_interfaces:
        ----------
        enp0s3:
            - fe80::8950:df02:ce9a:5ce0
        lo:
            - ::1
    ip_gw:
        False
    ip_interfaces:
        ----------
        enp0s3:
            - 192.168.56.6
            - fe80::8950:df02:ce9a:5ce0
        lo:
            - 127.0.0.1
            - ::1
    ipv4:
        - 127.0.0.1
        - 192.168.56.6
    ipv6:
        - ::1
        - fe80::8950:df02:ce9a:5ce0
    kernel:
        Linux
    kernelparams:
        |_
          - BOOT_IMAGE
          - /boot/vmlinuz-5.10.0-13-amd64
        |_
          - root
          - None
        |_
          - ro
          - None
        |_
          - quiet
          - None
        |_
          - splash
          - None
        |_
          - resume
          - None
    kernelrelease:
        5.10.0-13-amd64
    kernelversion:
        #1 SMP Debian 5.10.106-1 (2022-03-17)
    locale_info:
        ----------
        defaultencoding:
            UTF-8
        defaultlanguage:
            en_US
        detectedencoding:
            utf-8
        timezone:
            EEST
    localhost:
        derpMaster
    lsb_distrib_codename:
        bullseye
    lsb_distrib_description:
        Debian GNU/Linux 11 (bullseye)
    lsb_distrib_id:
        Debian
    lsb_distrib_release:
        11
    machine_id:
        83eceb54a10e42478f1240b30eaab954
    manufacturer:
        innotek GmbH
    master:
        salt
    mdadm:
    mem_total:
        3847
    nodename:
        derpMaster
    num_cpus:
        1
    num_gpus:
        1
    os:
        Debian
    os_family:
        Debian
    osarch:
        amd64
    oscodename:
        bullseye
    osfinger:
        Debian-11
    osfullname:
        Debian
    osmajorrelease:
        11
    osrelease:
        11
    osrelease_info:
        - 11
    path:
        /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
    pid:
        4479
    productname:
        VirtualBox
    ps:
        ps -efHww
    pythonexecutable:
        /usr/bin/python3
    pythonpath:
        - /usr/bin
        - /usr/lib/python39.zip
        - /usr/lib/python3.9
        - /usr/lib/python3.9/lib-dynload
        - /usr/local/lib/python3.9/dist-packages
        - /usr/lib/python3/dist-packages
        - /usr/lib/python3.9/dist-packages
    pythonversion:
        - 3
        - 9
        - 2
        - final
        - 0
    saltpath:
        /usr/lib/python3/dist-packages/salt
    saltversion:
        3002.6
    saltversioninfo:
        - 3002
        - 6
    serialnumber:
        0
    server_id:
        1244298838
    shell:
        /bin/bash
    ssds:
    swap_total:
        8464
    systemd:
        ----------
        features:
            +PAM +AUDIT +SELINUX +IMA +APPARMOR +SMACK +SYSVINIT +UTMP +LIBCRYPTSETUP +GCRYPT +GNUTLS +ACL +XZ +LZ4 +ZSTD +SECCOMP +BLKID +ELFUTILS +KMOD +IDN2 -IDN +PCRE2 default-hierarchy=unified
        version:
            247
    systempath:
        - /usr/local/sbin
        - /usr/local/bin
        - /usr/sbin
        - /usr/bin
        - /sbin
        - /bin
    uid:
        0
    username:
        root
    uuid:
        06435416-f8f6-9644-8095-45a861dbcd7a
    virtual:
        VirtualBox
    zfs_feature_flags:
        False
    zfs_support:
        False
    zmqversion:
        4.3.4
```
Koneesta kiinnostavia tietoja tulosteessa:  
Käyttöjärjestelmä on 64-bittinen Linux Debian 11 Bullseye, kyseessä on Virtualboxilla pyörivä virtuaalikone. 
Vapaan muistin määrä tällä hetkellä 3847MB.   
Prosessori (tässä tapauksessa isäntäkoneen) on Intel(R) Core(TM) i5-7300HQ CPU @ 2.50GHz joka noudattaa x86_64 arkkitehtuuria.  
Tulosteesta selviää, myös laitteen nimi derpMaster sekä sen ipv4/6 osoitteet ja mm. saltin versio 3002.6.
  
Kaikenkaikkiaan tuloste antaa todella paljon tietoa ja itselleni ei ole ihan selvää, mikä kaikki siitä on tärkeää.

## c) Kultajyvät. Laadi komento, joka näyttää koneesta vain tärkeimmät tiedot (grains.item)
   
```
pajazzo@derpMaster:$ sudo salt-call --local grains.item host lsb_distrib_description cpu_model disks domain mem_total saltversion virtual username 
local:
    ----------
    cpu_model:
        Intel(R) Core(TM) i5-7300HQ CPU @ 2.50GHz
    disks:
        - sr0
        - sda
    domain:
    host:
        derpMaster
    lsb_distrib_description:
        Debian GNU/Linux 11 (bullseye)
    mem_total:
        3847
    saltversion:
        3002.6
    username:
        root
    virtual:
        VirtualBox
```
Oheiseen komentoon laitoin edellisestä kohdasta sellaisia tietoja joiden näkisin olevan hyödyllisiä näin näppituntumalta ajateltuna.  
  
## d) Idempotenssi. Tee idempotentti esimerkkikomento saltilla. Aja komentoa useita kertoja. Osoita selitetyin esimerkein, että komentosi on idempotentti.
  
  
  
## e) Omat mausteet. Kokeile jotain uutta (ei aiemmin kurssilla näytettyä) ominaisuutta kustakin tärkeimmästä tilafunktiosta pkg, file, service, user.

## f) Herra ja orja. Asenna Salt master-slave arkkitehtuurilla. Anna orjalle komento. (Tämä tehtävä lienee hieman haastavampi) Update 2022-03-31: Voit asentaa tässä molemmat, herran ja orjan, samalle koneelle.

## h) Vapaaehtoinen: kokeile Saltia Windowsissa.

## i) Vapaaehtoinen: kokeile herra-orja -arkkitehtuuria verkon yli, niin että herra ja orja ovat eri koneilla. Voit laittaa ne myös eri virtuaalikoneille. 

## j) Vapaaehtoinen: lisää koneeseen vielä yksi orja, joka on eri koneella. 

## k) Vapaaehtoinen: asenna ja tee asetukset jollekin palvelimelle (Apache, SSHd...) Saltilla. (pkg-file-service)

Vinkkejä:

  - Karvinen 2006: Raportin kirjoittaminen
  - Mikä meininki? 'cat /etc/*version /etc/*release', 'uname -a', 'sudo
    salt-call --version' (tai grainsilla)
  - Tietoja koneesta: grains.items, grains.item
  - Ohjeita 'sudo salt-call --local sys.state_doc|less'
  - Omat mausteet: ohje yhdestä funktiosta 'sudo salt-call --local
    sys.state_doc pkg'
  - Herra ja orja
      □ Voit tehdä VirtualBoxin graafisesta käyttöliittymästä kaksi konetta, ja
        niiden välille virtuaalisen verkon. File: Virtual Network Manager...
      □ Voit myös käyttää VirtualBoxia Vagrantilla. Se toiminee parhaiten, kun
        Host OS on Linux, ja ajat vagrant-komkennot suoraan raudalta (host
        OS:ssa).
  - Jos salt-master ei vastaa, katso, että se on käynnistetty 'sudo systemctl
    start salt-master'
  - Päivitin muutamaa kohtaa 2022-03-31 niin, että myös helpommat versiot
    tehtävistä kelpaavat. Jos ehdit tehdä edelliset versiot, hienoa, ne
    kelpaavat myös.
  - Vaikeita kohtia? Ratko kaikki mitä osaat, raportoi ja palauta ajoissa.
    Vaikeasta tai kesken jääneestä kohdasta erityisen tarkka raportti: mitä
    teit, mitä tapahtui. Ota ruutukaappaukset ja sanatarkat virheilmoitukset
    talteen. Mistä arvelet ongelman johtuvan? Mitä ratkaisuvaihtoehtoja vielä
    voisi kokeilla? Löydätkö (esim virheilmoituksella hakemalla) lähteitä,
    joissa ehdotetaan ratkaisuja? Ja katsotaan yhdessä tunnilla loput.
