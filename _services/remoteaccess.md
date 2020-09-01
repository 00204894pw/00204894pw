---
title: "Dostęp zdalny SSH i Samba"
date: 2018-11-28T15:14:54+10:00
featured: true
weight: 5
---

## Stałe IP






## SSH






## Samba

### Instalacja

sudo apt update
sudo apt install samba

### Weryfikacja
Weryfikacja poprawności instalacji:

whereis samba

### Dodanie ścieżki HA

sudo nano /etc/samba/smb.conf

[sambashare]
    comment = Samba on Ubuntu for HA
    path = /home/username/moro
    read only = no
    browsable = yes

udo service smbd restart
sudo ufw allow samba

### Set password

sudo smbpasswd -a username

### Connect from windows
File Manager
\\ip-address\sambashare

Włącz sambę na Windows 10 ‘SMB1.0/CIFS File Sharing Support’

## HA Login

Dostęp do HA realizowany jest przez interfejs graficzny (GUI) dostępny z poziomu przeglądarki internetowej.
Będąc w obrębie jednej sieci LAN uruchom przeglądarkę i wejdz na adres http://SERWERIP:8123


- Jak ustawić automatyczny start usługi HA po restarcie systemu? >> [#TODO]
- Jak sprawdzić IP jednostki HA? 
    1. logujemy się na serwer 
    2. uruchamiamy polecenie ifconfig
    3. odczytujemy IP z odpowiedniego interfejsu sieciowego

![HA Login Img](/images/HA_login.png)
Ekran logowania

![HA Dashboard Img](/images/HA_dashboard.png)
Ekran logowania