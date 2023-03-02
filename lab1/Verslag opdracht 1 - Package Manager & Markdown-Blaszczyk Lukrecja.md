## Problemen en oplossingen

Tijdens het uitvoeren van de opdracht wou Powershell eerst mijn script niet uitvoeren. Na het doornemen van de instructies probeerde ik het Policy-commando in te voeren maar in het verkeerde venster. Na enig denkwerk en met de hulp van de instructies loste ik het probleem zelf op. Dat was het enig probleem dat ik ben tegen gekomen tijdens het uitvoeren van de opdracht.

## Taken:

1. Een lijst tonen van de software die nu geïnstalleerd via Chocolatey
	1. Choco List
2. Alle packages die nu geïnstalleerd zijn bijwerken tot de laatste versie
	1. Choco Upgrade
3. Via de console een package opzoeken
	1. Choco Find
4. Een geïnstalleerde applicatie verwijderen
	1. Choco Uninstall

## Installatiescript
```
# Automatiseren software-installatie
Write-Host "Installatie algemene applicaties"
choco install -y git
choco install -y adobereader
choco install -y firefox
choco install -y github-desktop
choco install -y vscode
choco install -y vlc
Write-Host "Software voor System Engineering Lab"
choco install -y filezilla
choco install -y virtualbox
choco install -y mysql.workbench
```


