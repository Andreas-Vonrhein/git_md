# Verzeichnise / Dateien nicht ins Repo aufnehmen 
Wenn Dateien nicht ins Repo aufgenommen werden soll, gibt es zwei Möglichkeiten. 
## Möglichkeit: Die Datei .gitignore 
Diese Datei kann in jedem Verzeichnis des Repos liegen. Es wird auf die Hierachie geachtet. Die .gitignore Datei im aktuellen Verzeichnis überschreibt die die .gitignore Datei im darüberliegenden Verzeichnis. 
In der Datei werden "Patterns" gespeichert. Jede Zeile enthält ein Pattern. 
Diese Datei wird mit ins Repo übernommen und somit auch "geteilt" 
## Möglichkeit: Die Datei: .git/info/exclude 
In dieser Datei werden ignores definiert, die speziell nur für diesen Workspace sind und nicht mit anderen geteilt (für die Allgemeinheit) werden. 
## Anwendung 
in die `.gitignore` kommen allgemeine Ignore Anweiseungen, die für alle Teammitglieder sinnvoll sind z.B. 
- Kompilierte Dateien 

Die Datei `.gitignore` wird auch von git im Repository gespeichert und wird somit an alle verteilt 
in die `.git/info/exclude` Datei kommen individuelle ignore-Anweisungen, die nicht im Repo gespeichert werden. Dies mach Sinn bei: 

- Individuellen Einstellungen bei der IDE (z.B. das .vscode verzeichnis) 
- Eigene Beispieldateien an denen man das Programm testet 
- Local bezogene Dateien, die einen absoluten Pfad besitzen (dieser ist ja nicht bei allen Teammitgliedern gleich) 

# Pattern 

| Pattern | Bedeutung |
| :---: | --- |
| #      | leitet einen Kommentar ein  |
| \#     | ist kein Kommentar, das Pattern beginnt mit # 
| /      | Seperator für Pfadangaben 
| !      | Negiert die Zeile 
| \*     | alles (außer / ) 
| ?      | Genau ein Zeichen (außer / ) 
| [a-z]  | Bereichsangaben in eckigen Klammern 

## Beispiele
| Eintrag | Erklärung |
| --- | --- |
|/Verzeichnis1/verzeichnis2 | absoluter Dateipfad
|Verzeichnis/ | relativer Pfad zur `.gitignore` Datei
| \*.log | alle \*.Log Dateien
| Verzeichnis/\*.log | alle \*.log Dateien in genau diesem Verzeichnis. Darunterliegende Verzeichnisse werden die \*.log Dateien aber berücksichtigt
|Verzeichnis/\**/*.log | alle \*.log Dateien auch in den Unterverzeichnissen.
|!ToDo.md| die ToDo.md Datei wird berücksichtigt
|!\*[Tt][Oo][Dd][Oo]\*| Alles was irgendwie ToDo lautet wird berücksichtigt. Ob Groß oder klein ist egal. Die \* sorgen dafür, dass die Zeichenfolge TODO irgendwo vorhanden sein muss. Also *todo.md* genauso wie *tOdO1.txt*
 
# Überprüfen der Ignore-Einstellungen 
```bash
git check-ignore -vn check-ignore <Datei oder Verzeichnis> 
```
Sollte keine Rückgabe erfolgen, so wird die Datei von git überwacht. 
Solte eine ignore-Regel vorhanden sein, so erhält man eine Ausgabe mit der Datei und Zeilennummer in welcher das Ignore-Regel steht. 
## Beispiel:
```bash
git check-ignore -vn check-ignore .vscode/tasks.json 
```

### Ausgabe, wenn in der `.gitignore` Datei
~~~ bash
::      check-ignore 
.gitignore:19:.vscode/  .vscode/tasks.json 
~~~
### Ausgabe, wenn in der `.git/info/exclude` Datei
~~~ bash
::      check-ignore 
.git/info/exclude:8:.vscode/    .vscode/tasks.json 
~~~
