# labo 1

## Linux

![Alt text](linux/linux_bash_script.png "Screenshot terminal")


| Taak | Commando |
|------|-----------|
| Een lijst tonen van de software die nu geinstalleerd is via apt | apt list --installed |
| Alle packages die nu geinstalleerd zijn bijwerken tot de laatste versie | sudo apt update && sudo apt upgrade -y |
| Via de console een package opzoeken | apt list "name" -a |
| Een geinstalleerde applicatie verwijderen | sudo apt remove "name" |

### Script

Aangezien Linux in WSL loopt en vooral Windows of evtl. MacOS voor SEL gaan gebruikt worden. Een verkorte versie van het script:

```bash
#! /bin/bash
# Automatiseren van Software installatie

echo "=== Bijwerken lijst beschikbare applicaties ==="
sudo apt -y update

echo "=== Algemene applicaties ==="
echo "### Nothing to install now ###"
```

## Mac

