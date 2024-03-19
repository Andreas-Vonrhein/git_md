# Datei zum Zeitpunkt des letzten commits wiederherstellen
~~~bash
git restore \<Datei\>
~~~
Die Datei wird zum Zeitpunkt des letzten commits wiederhergestellt. Alle Änderungen werden überschrieben und sind auch nicht mehr rückgängigmachbar.
Mit git status anzeigen lassen, welche Dateien für den aktuellem commit vorgemerkt sind. Es werden die Möglichkeiten angezeigt, mit denen man Dateien wiederherstellen kann. Zum Zeitpunkt des letzten commits.
Sollen alle Änderungen in allen Dateien rückgängig gemacht werden. Lautet der Befehl:
~~~bash
git restore .
~~~
 Alternative: 
 ~~~bash
 git checkout -- <Datei>
~~~
 
# Datei aus dem Arbeitsverzeichnis und dem Repo löschen
~~~bash
git rm <Dateiename>
~~~
 Die Datei wird auch aus dem Arbeitsverzeichnis gelöscht. Wiederherstellen mit restore?

# Datei im Arbeitsverzeichnis behalten aber im Repo/Stage entfernen
~~~bash
git reset \<Dateiname\>
~~~
Die Datei wird aus dem Stage bereich entfernt, bleibt aber im Arbeitsverzeichnis vorhanden
Dieser Befehl ist das Gegenteil von `git add <Datei>`
[git add](../git%20-%20GitHub_GitLab/04_Tägliche%20git%20Befehle.md#dateien-zum-repo-hinzufügen)
# Den letzten commit wiederrufen
~~~bash
git revert HEAD
~~~
 Es wird vom aktuellen Stand ausgegangen und der letzte commit wiederrufen.
Am besten vorher mit `git log --oneline` das Log anschauen.
Sollen mehrer commits wiederrufen werden, muss ein Bereich angegeben werden. Der Übersichthalber sollte auch der `revert` ohne commit (Option --n) ausgeführt werden. Dieser muss dann am Schluss händisch angestoßen werden. Somit wird dann auch nur eine commit-message gespeichert.
~~~bash
git revert -n HEAD~2^..HEAD
git commit -m "die letzten drei commits auf einmal rückgängig gemacht"
~~~
 **Erklärungen zu `revert`** 
|Option|Erklärung|
| :----------:| --- | 
|-n | -- no-commit 
| ^ | HEAD~2 soll inklusive sein
| .. | Bereichsangabe
