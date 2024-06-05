# LF9

# Statische IP
Um die IP statisch einzustellen muss man folgendes machen :
```
sudo nmcli c mod "Wired connection 1" ipv4.addresses 192.168.100.188/24 ipv4.method manual
sudo nmcli con mod "Wired connection 1" ipv4.gateway 192.168.100.1
sudo nmcli con mod "Wired connection 1" ipv4.dns "192.168.100.64"
```
# Benutzer erstellen
 Benutzer "willi" ohne Adminrechte:
```
sudo adduser willi
```
Benutzer "fernzugriff" mit Adminrechten:
```
sudo adduser fernzugriff
```
```
sudo usermod -aG sudo fernzugriff
```
# SSH-Dienst 
## 1. SSH installieren
```
sudo apt update
sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
```
## 2. "Fernzugriff" hinzufügen
```
sudo nano /etc/ssh/sshd_config
AllowUsers fernzugriff
sudo systemctl restart ssh
```
 
