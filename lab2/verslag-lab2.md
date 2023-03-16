# Labo 2 - MySQL

## Stap 1 - VirtualBox configureren

In VirtualBox -> Network Manager waren de IP adressen al correct ingesteld.
Geen problemen ondervonden.

## Stap 2 - Virtuele machine aanmaken

Bart & Lukrecja: ISO installatie
Azra & Isaac: VDI bestand

Geen foutmeldingen. Geen problemen bij het instellen van het vaste IP adres

### Optionele instellingen:

- Screen Lock: ok
- Automatisch inloggen: ok
- sFTP Server ingesteld: ja (https://linuxhint.com/setup-sftp-server-ubuntu/)

## Stap 3 - Configuratie databankserver

Enkele groepsleden hadden hulp nodig bij het aanpassen van het configuratiebestand.

### Configuratie van de databank

Bij MacOS was het eventjes zoeken naar het @ symbool in VirtualBox.

### Taakverdeling

2x Teams meeting waar we samen de configuratie doorlopen hebben.
Verslag: Bart

### Vragen

|Vraag|Antwoord|
|----|----|
|Waaraan zie je welke netwerkpoorten in gebruik zijn? | Bij State: LISTEN voor de MySQL daemon staat als adres enkel 127.0.0.1 |
|Had de wijziging van het config bestand effect? | Ja, er is een LISTEN voor MySQL daemon met adres 0.0.0.0 |



