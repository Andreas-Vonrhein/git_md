# Anleitung zur Installation und Einrichtung von GitHub auf Windows

##  GitHub-Konto erstellen

1. Besuche [GitHub](https://github.com/) in deinem Webbrowser.
2. Klicke auf "Sign up" (Registrieren), um ein neues Konto zu erstellen.
3. Folge den Anweisungen zur Erstellung deines Kontos. Stelle sicher, dass du eine gültige E-Mail-Adresse verwendest.

##  Git installieren

1. Besuche die [Git-Website](https://git-scm.com/) in deinem Webbrowser.
2. Lade die neueste Version von Git für Windows herunter.
3. Öffne die heruntergeladene Datei und folge den Installationsanweisungen.
4. Wähle während der Installation die Standardoptionen aus, es sei denn, du benötigst spezifische Anpassungen.

##  Git konfigurieren

1. Öffne die Git Bash-Anwendung, die mit der Git-Installation installiert wurde.
2. Konfiguriere deinen Benutzernamen, indem du den folgenden Befehl eingibst und deine GitHub-Benutzername ersetzt:
    
    arduinoCopy code
    
    `git config --global user.name "Dein GitHub-Benutzername"`
    
3. Konfiguriere deine E-Mail-Adresse mit dem folgenden Befehl und ersetze "deine-email@Beispiel.com" durch die E-Mail-Adresse, die mit deinem GitHub-Konto verknüpft ist:
    
    arduinoCopy code
    
    `git config --global user.email "deine-email@example.com"`
    

  GitHub Repository klonen

1. Öffne die Git Bash-Anwendung.
2. Navigiere zum Verzeichnis, in dem du das Repository klonen möchtest, indem du den `cd`-Befehl verwendest.
3. Klonen Sie das Repository, indem Sie den folgenden Befehl eingeben und die URL durch die URL des zu klonenden Repositories ersetzen:
    
    bashCopy code
    
    `git clone <Repository-URL>`
    

## GitHub Repository erstellen und verwalten

1. Gehe zu [GitHub](https://github.com/) und logge dich in dein Konto ein.
2. Klicke auf das "+"-Symbol in der oberen rechten Ecke und wähle "New repository" (Neues Repository).
3. Gib einen Namen für dein Repository ein, wähle die gewünschten Optionen aus und klicke auf "Create repository" (Repository erstellen).
4. Folge den Anweisungen, um dein lokales Repository mit GitHub zu verknüpfen und deine Änderungen hochzuladen.
