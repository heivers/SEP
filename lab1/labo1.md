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

### Script

```bash
#! /bin/bash

# Automatiseren software-installatie
echo "=== Dit script installeert de nodige software voor Sys Engineering Lab ==="

brew install --cask virtualbox
brew install --cask cyberduck
brew install --cask mysqlworkbench
````
### resultaat

```bash
(base) barts-mbp:macOS bartheerkens$ ./installatie.sh 
=== Dit script installeert de nodige software voor Sys Engineering Lab ===
Running `brew update --auto-update`...
==> Auto-updated Homebrew!
Updated 1 tap (heroku/brew).

You have 5 outdated formulae installed.
You can upgrade them with brew upgrade
or list them with brew outdated.

Warning: Cask 'virtualbox' is already installed.

To re-install virtualbox, run:
  brew reinstall --cask virtualbox
==> Downloading https://update.cyberduck.io/Cyberduck-8.5.6.39394.zip
==> Downloading from https://a48823c7ec3cf4539564-60c534a1284a12ce74ef84032e9b4e46.ssl.cf1.rackcdn.com/Cyberduck-8.5.
######################################################################## 100.0%
==> Installing Cask cyberduck
==> Moving App 'Cyberduck.app' to '/Applications/Cyberduck.app'
🍺  cyberduck was successfully installed!
==> Downloading https://cdn.mysql.com/Downloads/MySQLGUITools/mysql-workbench-community-8.0.32-macos-x86_64.dmg
######################################################################## 100.0%
==> Installing Cask mysqlworkbench
==> Moving App 'MySQLWorkbench.app' to '/Applications/MySQLWorkbench.app'
🍺  mysqlworkbench was successfully installed!
```



