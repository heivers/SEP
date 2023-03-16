# Labo 3 - Webserver opzetten

## Achtergrondinfo

Zonder Webserver geen gehostete sites. Ondertussen zijn er verschillende Stacks. Een van de meestgebruikte is nog altijd LAMP (Linux, Apache, MySql, PHP). Het Apache deel gaan we in dit labo configureren.
side note: Ubuntu heeft zelfs een lamp package omdat het zoveel gebruikt wordt.

## Stap 1 - Installatie

- We beginnen met een Snapshot te maken van de VM.
- Installeren van Apache2
  - sudo apt-get update && sudo apt-get install apache2 -y
- Nakijken of de service gestart is, netwerkpoorten.
  - systemctl status apache2 (vendor-preset = enabled -> service start automatisch)
    - of service --status-all (een + wil zeggen service gestart)
    - of webbrowser openen en 127.0.0.1 proberen te bereiken.
  - ss -tlnp laat een * zien bij poort 80 (http), er wordt dus naar alle adressen geluisterd.
    - via de hostmachine is het ook mogelijk 192.168.56.20 te openen in een webbrowser.
- Controle standaardwebsite
  - in vorige stap reeds doorgevoerd
- Document root voor website: /var/www/html (grep -i "DocumentRoot" /etc/apache2/sites-available/000-default.conf)

## Stap 2 - Een statische website publiceren

- berechtigen juist zetten: 
    - sudo usermod -aG www-data "username"
    - sudo chgrp www-data /var/www/html
    - sudo chmod g+w /var/www/html
    - na het kopieren van de website lezerechten voor deze files aan www-data toegekend
- SSL
  - in het vorige labo hadden we een sftp server opgezet. Die was zo geconfigureerd dat enkel sftp verbindingen geaccepteerd werden en de gebruiker tot zijn home drive beperkt was -> sshd_config file veranderd -> ssh en scp toegelaten.

## Stap 3 - een webserver beveiligen met SSL

    ```
    #ssl aktiveren
    sudo a2enmod ssl
    sudo awensite default-ssl
    # service opnieuw starte
    sudo systemctl reload apache2
    ```
- Netwerkpoort voor https = 443
  - bij ss -tlnp is er buiten de LISTEN poort 80 nog een poort 443 bijgekomen

## Stap 4 - een webserver beveiligen met een firewall

- Netwerkpoorten nakijken:
  - ssh -> 22
  - http -> 80
  - https -> 443
  - MySql -> 3306

- Firewall instellen
    ```bash
    sudo apt install ufw gufw
    sudo ufw allow apache | ssh | mysql | 443 (achtereenvolgens)
    ```

## Stap 5 - een webserver beveiligen met fail2ban

- Installatie
  ```bash
  sudo apt install fail2ban
  ```
- Aktivatie:
  
  ```
  sudo systemctl enable fail2ban
  ````
  -> vendor preset (enabled)

- Configuratie van fail2ban
  - enkel Jail voor ssh in config file gelaten
- |attribuut|uitleg|
  |----|----|
  |findtime|de tijdspanne waarbinnen maxretries geldt. bv: findtime 10m, maxretries: 10. Als binnen 10 minuten meer als 10 keer een ongeldige actie plaatsvindt, word gebanned|
  |maxretry|max. aantal herhalingen binnen findtime|
  |bantime|de tijd dat de "aanvaller" geblokkeerd wordt|

  - ssh-config
  ```
  findtime = 3m
  bantime = 15m
  maxretry = 6
  ````
  - test ssh:
    - ssh vboxuser@192.168.56.20 -> ok
    - na 6 foute pogingen: gebeurd niks, bij volgende verbinding -> Connection refused
  - Fail2Ban command line:
- |vragen|commando|
  |------|--------|
  |geconfigureerde jails| sudo fail2ban-client status|
  |Welke ip adressen geblokkeerd| sudo fail2ban-client banned|
  |opties opvragen van sshd jail| sudo fail2ban-client get sshd "optie bv findtime"|
  |ip adres terug vrijmaken| fail2ban-client unban IP |
  - Exception:
    - sudo fail2ban-client set sshd addignoreip 192.168.56.30




  