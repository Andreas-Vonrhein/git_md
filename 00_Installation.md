
# Pakete in Linux installieren (funktioniert auch mit Windows)
```bash
apt-get install git 
```
oder
```bash
apt-get install git-all 
```

# Name und Email hinterlegen 
```bash
git config --global user.name "Name" 
git config --global user.email "Email"  
```
Diese Informationen werden genutzt um bei commits den Bearbeiter zu setzen.
 
# Account auf GitHub erstellen 
www.github.com 

# Login auf SSH umstellen 
## Schlüssel erzeugen
SSH-Key erzeugen und den Public key in GitHUB hochladen 
```bash
ssh-keygen –b 4096 
```
 
## SSH- key in der config hinterlegen 
In Datei: `.ssh/config` 
```bash
Host github.com 
  IdentityFile ~/.ssh/privatKeyForGitHub 
```

Wenn verschiedene keys verwendet werden sollen. Z.B. für Arbeitsrepos: 
Zusätzlich eintragen: 
```bash
Host github-work.com 
  Hostname   github.com 
  IdentityFile  ~/.ssh/privateKeyForGitHubWork 
```
Dann muss beim ersten `git clone` die Url github-work verwendet werden. Damit die Umleitung zum anderen Key funktioniert. 
```bash
git clone git@github-work.com:ACCOUNT/REPO.git 
```
 
# Repository auf SSH umstellen 
```bash
git remote set-url origin git@github.com:ACCOUNT/REPO.git 
```
 

 
