# Oppsetning av Operativsystem og Program på Rasberry Pi



## OBS: Pass på at cmd i windows og terminalen i linux bruker noen ulike kommandoer


## 1. Last ned Raspberry Pi imager på pc-en din og putt inn sd kortet.

    a. Velg din raspberry pi device
    b. Velg ønsket operativsystem (Linux Ubuntu Desktop i vårt tilfelle)
    c. Velg sd kortet som er inne i pc-en og trykk "next"


## 2. Sett inn sd-kortet i Rasberry Pi-en og begynn installering

* "Husk mus, tastatur og tilkobling til skjerm for raspberry pi-en!" Set opp ønsket språk og tastaturoppsett.
* Lag brukeren din.
* Åpne terminalen med CTRL + ALT + T
* Skriv `sudo apt update` og vent på at den blir ferdig,
deretter skriv `sudo apt upgrade`og vent på at den blir ferdig.

## 3. Sett opp brannmur med UFW (uncomplicated firewall)
Skriv dette i terminalen:
```
sudo apt install ufw (installerer UFW)

sudo ufw enable (Aktiverer brannmuren på oppstart)

sudo ufw allow ssh (Gir tillatelse for SSH-tilkoblinger gjennom brannmuren)

(Du kan sjekke statusen på brannmuren senere ved å skrive sudo ufw status i terminalen)
```
## 4. Skru på SSH
I terminalen:
```
sudo apt install openssh-server (installer SSH-serveren)
sudo systemctl enable ssh (gjør sånn at SSH skrur seg på ved oppstart)
sudo systemctl start ssh (starter SSH med en gang)
```
* For å koble til pi-en via pc, åpne CMD i windows med Windows + R og skriv 'cmd' på pi-en skriver du `ip a` og let etter en IP-adresse som begynner med 10.2.1.x eller noe lignende (x skal være et nummer mellom 2 og 254)

## 5. Installering av programvare
```
sudo apt install python3-pip (Installerer python på pi-en)

sudo apt install git (Installerer git på pi-en)

sudo apt install mariadb-server (Installerer mariadb på pi-en)

sudo mysql_secure_installation (Installerer mysql på pi-en)
```
## 6. Lage bruker i MariaDB
```
* *sudo mariadb -u root* (åpner MariaDB i terminalen)
**OBS: Husk at alle kommandoer slutter med ";" i mariadb**

* CREATE USER 'username@localhost' IDENTIFIED BY 'password'; (bytt utt username med ditt brukernavn og password med ditt eget passord)

* GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'password'; (Gir brukeren rettigheter)

* FLUSH PRIVILEGES; (Oppdaterer rettighetene)
```

(For å gå ut av mariadb kan du skrive "exit" eller trykke CTRL + D)

## 7. Installer annen programvare du ønsker. Som VS Code, en annen nettleser, wireshark osv.

* Hvis du får trøbbel med VS Code, last ned .deb for arm64 fra https://code.visualstudio.com/docs/setup/linux Naviger deretter til mappen du lastet ned filen

* Skriv `sudo apt install ./code` og trykk tab, så enter

## 8. Slutten av guiden

* Kjør `sudo apt update` og `sudo apt upgrade` igjen

For å koble til med ssh fra laptop til pi-en skriver du i terminalen:

* `ssh brukernavn@ip`

(Bytt ut brukernavn med ditt eget brukernavn og ip med raspberry pi-en sin ip adresse)

## 9. Ekstra

Vanlige shell-kommandoer:

* `ls`  (lister filer og mapper i det gjeldende katalogen)
* `cd` (endrer arbeidskatalogen "navigerer mellom mapper")
* `cd` .. (Endrer mappe til mappen under)
* `pwd` (Viser den gjeldende arbeidskatalogens fullstendige sti.)
* `mkdir` (Oppretter en ny mappe "Directory")
* `rm` (Fjerner filer eller mapper)
* `cp` (Kopierer filer eller mapper)
* `mv` (Flytter eller gir nytt navn til filer eller mapper)
* `chmod` (Endrer tillatelser på filer eller mapper)
* `sudo` (Utfører en kommando med administrative rettigheter)
* `man` (Viser manualen for en kommando)

