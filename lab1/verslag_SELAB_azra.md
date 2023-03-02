# windows

---

## Problemen en oplossingen

Tijdens mijn labo wou powershell mijn script niet uitvoeren, de commando "Set-ExecutionPolicyBypass-ScopeProcess" heeft me hierbij geholpen.

---

## Vragen

- promt: c:\windows\system32
- mijn script: C:\Users\capan\OneDrive - Hogeschool Gent\SELAB\Untitled1.ps1
- Script in screenshot: D:\Users\BertVV\Documents\HoGent\SELab\Installatie.ps1

---

## Chocolaty

- Een lijst tonen van de software die nu geïnstalleerd via Chocolatey
  : Choco List-l
- Alle packages die nu geïnstalleerd zijn bijwerken tot de laatste versie
  : Choco Upgrade all
- Via de console een package opzoeken
  : Choco Find "name"
- Een geïnstalleerde applicatie verwijderen
  : Choco Uninstal "name"

  ***

#Automatiseren software-installatie

Write-Host "Installatie algemene applicaties"

choco install -y git

choco install -y MySQL Workbench

choco install -y Visual Studio Code

choco install -y VirtualBox

choco install -y Adobe Acrobat Reader
