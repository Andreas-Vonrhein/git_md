ich glaube hier ist irgendwo ein Fehler drin.

# Locales Repo anlegen
Wechsele in das Verzeichnis
~~~bash
git init
git add DATEINAMEN
git commit --m 'initial commit'
~~~
 
# Locales Repo mit server verbinden
~~~bash
git remote add origin git@github.com:andreas-vonrhein/REPONAME.git
git remote add origin https://github.com:andreas-vonrhein/REPONAME.git
~~~

# Verbindung zu Server verifizieren
~~~bash
git remote -v
~~~
 
# Branch auf main legen (bei alter version master)
~~~bash
git branch --M main
~~~

~~~shell
git branch --set-upstream-to=origin/main main
~~~


# Locales Repo auf server hochladen
~~~bash
Git push --u origin main
~~~
 Die Option --u legt den default upstream fest*

# Mehrer Remote Repos verwenden
Man kann sein Lokales Repo mit mehreren verschiedenen remote Repos verbinden. Allerdings müssen die Repo namen unterschiedlich sein. ORIGIN ist meistens das erste Repo (auf GitHub verwendet). Man kann dann zusätzlich zu GitHub auch noch mit GitLab syncen.
~~~bash
git remote add gitlab git@gitlab.com:\<account\>/\<repo\>.git
git push gitlab \--all
~~~
 Beim `git push` muss dann aber immer expliziet das repo GITLAB angegeben werden
Die Configuration findet sich in .git/config im workspace.

 
