# LF9

# Statische IP
Um die IP statisch einzustellen muss man folgendes machen :
```
sudo nmcli c mod "Wired connection 1" ipv4.addresses 192.168.24.188/24 ipv4.method manual
sudo nmcli con mod "Wired connection 1" ipv4.gateway 192.168.24.1
sudo nmcli con mod "Wired connection 1" ipv4.dns "192.168.24.64"
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
## SSH installieren
```
sudo apt update
sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
```
## "Fernzugriff" hinzufügen zu SSH
SSH-Dienst konfigurieren
```
sudo nano /etc/ssh/sshd_config
```
Fernzugriff hinzufügen
```
AllowUsers fernzugriff
```
SSH-Dienst neu starten
``` 
sudo systemctl restart ssh
```
# Docker und Docker Compose installieren
```
sudo apt-get update
sudo apt-get install docker.io docker-compose
```
# Web-App 
```
git clone https://github.com/Hiddensarnek/LF9-AlexPaul.git
cd LF9-AlexPaul
sudo docker-compose up -d
```
Nun kann man die Web-App mit  http://192.168.24.188:5000 erreichen.
