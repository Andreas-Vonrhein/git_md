# Dateien zum Repo hinzufügen

```bash
git add <Dateiname>
```

Das Gegenteil zu diesem Befehl ist git reset \<Datei>
[git reset](../git%20-%20GitHub_GitLab/06_Tägliche%20git_%20Wiederherstellung%20_%20Undo.md#datei-im-arbeitsverzeichnis-behalten-aber-im-repostage-entfernen)
# Zwischenstand im localen Repo speichern

```bash
git commit --a --m 'Text'
```

Optionen:  
m= Commit Kommentar  
a= alle Dateien die bereits im Repo sind werden überprüft und bei Bedarf im Repo aktualisiert

## den getätigten commit erweitern

Um einen bereits getätigten commit zu erweitern, weil man z.B. eine Datei vergessen hat. Der commit darf aber noch nicht auf das Repo gepusht worden sein.

```bash
git commit --amend
```

&nbsp;

# Status eines Repos abfragen

```bash
git status
```

Anzeigen von Dateien

- die zum commit vorgemerkt sind.
- Die gelöscht wurden
- Die restored werden können

# Sync vom Server -> localen Repo

```bash
git pull
```

Immer zuerst vor dem upload, damit man einen merge machen kann.  
Im gegensatz zu git push werden alle Branches gepullt. Es wird aber nur das aktuelle Branch auch gemergt.

# Sync vom localen Repo -> Server

```bash
git push
```

Immer vorher vom Server mit (git pull) syncen, falls jemand anderes einen Upload gemacht hat.  
Es wird nur der aktuelle Branch gepusht. Sollen alle localen Branches gepusht werden muss man dies explizit angeben:

```bash
git push --all origin
```

&nbsp;

# Dateien im Repo umbenennen oder verschieben

```bash
git mv \<alterName\> \<neuerName\>
```

Wie in der bash kann man mit mv umbenennen und verschieben.  
Die Änderung wird erst nach dem nächsten commit wirksam.

# Dateien im Repo kopieren

Hierfür gibt es keinen Befehl.  
Auf der shell `cp` und dann ein `git add` durchführen

# Log anschauen

```bash
git log
```

Es werden alle Commits aufgelistet

```bash
git log ---oneline
```

Kurze und knappe anzeige in einer Zeile pro commit

# Änderungen am Code speichern aber nicht in des lokale Repo commiten

Wenn man an einem Code arbeitet und diese arbeit kurz unterbrechen muss, um z.B. einen Bugfix in einem anderen Branch zu machen.  
Hierzu werden die Änderungen gespeichert mit

```bash
git stash
```

Es werden alle Änderungen rückgäning gemacht. Das lokale Repo hat den stand des letzten commits, aber die Änderungen werden im Stash-Speicher hinterlegt. Somit sind sie nicht verloren.

# Gespeicherte Änderungen wieder laden

Die Änderungen müssen manuell wieder "geladen" werden.

```bash
git stash pop
```

&nbsp;

# Anwendung git stash

Es kann auch sein, dass man Änderugnen am Code gemacht hat und vor dem commit noch mal den Branch aktualisieren möchte. Dies ist nur möglich wenn es keine Änderungen am Code gibt. Deshalb speichert man die Änderungen mit git stash.

```bash
git stash
git pull
git stash pop
```

&nbsp;

# Dateien zu einem früheren Zeitpunkt anschauen

```bash
git show HEAD\~3:\<Datei\>
```

Die Datei wird in ihrem Zustand vor drei commits angezeigt

### Sollen nur die Änderungen angezeigt werden ist der Befehl `git diff`der richtige

```bash
git diff HEAD\~3 \<Datei\>
```

Unterschied zum akutellen Repo

```bash
Git diff HEAD\~3 HEAD \<Datei\>
```

Unterschied zwischen dem 3. letzten und dem letzten: