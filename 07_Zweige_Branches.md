Zum weiterentwickeln einen bereits veröffentlichten Projektes
1.  Branch: release
2.  Branch: testing
3.  Branch: developement

# Zweige/Branches erstellen und als aktiven Branch setzen
~~~bash
git checkout --b newBranchName
git push --set-upstream origin newBranchName
~~~
 Dateien ohne commit werden automatisch in den neuen Branch committed
Alle Änderungen betreffen nur noch den neuen Zweig, dies gilt auch für die täglichen Befehle.

# Den aktiven Zweig/Branch wechseln
~~~bash
git checkout branchName
~~~
 Hier können alle täglichen Befehle angewendet werden.

# Einen commit aus anderem Branch in den aktuellen Branch übertragen (z.B. Bugfix)
~~~bash
git checkout branchName
git cherry-pick commitID
~~~
 Jeder commit bekommt eine eindeutige ID. Diese kann mit dem cherry-pick in anderen Branches ebenfalls importiert werden

# Zweige/Branches vereinigen (mergen)
~~~bash
git checkout main
~~~
Zuerst muss in den ursprungs Branch gewechselt werden.
~~~bash
git merge branchNameToInclude
~~~
Es wird automatisch gemergt.
Sollte beim auto merge etwas schief gehen, bekommt man eine Fehlermeldung mit den betreffenden Dateinamen. Diese enthält dann den Ursprungscode und den Neuen Code. Dieser Konflikt muss dann manuel aufgelöst werden. Die resultierende Datei muss denn mit einem `git commit --a --m 'resolved merge conflict ...'` manuell in das Repo commitet werden.
Der manuelle Eintrag in der Datei sieht so aus:
~~~bash
<<<<< HEAD
Code des main Branches
=====
Code des newFeature Branches
>>>>> newFeatureBranchName
~~~
 
# Zweig/Branch löschen
~~~bash
git branch --d branchToDeleteName
~~~
 