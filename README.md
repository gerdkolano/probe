Erprobe git und github
=====
trying to find out how to use github Wie krieg' ich nun meine Dateien hier rein?

Den im Browser in https://github.com/gerdkolano/probe/edit/master/README.md eingetippten Text

kann ich mit

  git clone git://github.com/gerdkolano/probe.git
  
  fatal: Zielpfad 'probe' existiert bereits und ist kein leeres Verzeichnis.
  
wieder herausholen, wenn 'probe' noch nicht existiert.

git add probe

git commit probe https://github.com/gerdkolano

error: pathspec 'https://github.com/gerdkolano' did not match any file(s) known to git.

git fetch git://github.com/gerdkolano/probe.git

liefert nicht die hier getippten Änderungen.

Erst mit einem "jungfräulichen" "repository" https://github.com/gerdkolano/dlf habe ich Erfolg.


Nach probe.git kann ich nichts hochladen.

git push probe master
 
Username for 'https://github.com': gerdkolano

Password for 'https://gerdkolano@github.com': 

To https://github.com/gerdkolano/probe.git

 ! [rejected]        master -> master (fetch first)

error: Fehler beim Versenden einiger Referenzen nach 'https://github.com/gerdkolano/probe.git'

Hinweis: Aktualisierungen wurden zurückgewiesen, weil das Remote-Repository Commits enthält,

Hinweis: die lokal nicht vorhanden sind. Das wird üblicherweise durch einen "push" von

Hinweis: Commits auf dieselbe Referenz von einem anderen Repository aus verursacht.

Hinweis: Vielleicht müssen Sie die externen Änderungen zusammenzuführen (z.B. 'git pull ...')

Hinweis: bevor Sie erneut "push" ausführen.

Hinweis: Siehe auch die Sektion 'Note about fast-forwards' in 'git push --help'

Hinweis: für weitere Details.

So geht's:

    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ cd /zoe-home/zoe-hanno/android/Deutschlandfunk
    # hier gibt es .git und README.md
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git add --all favoriten  | cat
    # überflüssig: git remote add origin https://github.com/gerdkolano/dlf.git
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git remote -v # zeigt origin	
    https://github.com/gerdkolano/eutschlandfun.git (fetch) und (push)
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git add --all favoriten  | cat
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git commit
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git push -u origin master # antwortet mit
    # Username for 'https://github.com': gerdkolano
    # Password for 'https://
    gerdkolano@github.com':
    # Counting objects: 51, done.
    # Delta compression using up to 4 threads.
    # Compressing objects: 100% (20/20), done.
    # Writing objects: 100% (29/29), 378.28 KiB | 0 bytes/s, done.
    # Total 29 (delta 13), reused 0 (delta 0)
    # To https://github.com/gerdkolano/eutschlandfun.git
    #    b121bcc..542314a  master -> master
    # Branch master konfiguriert zum Folgen von Remote-Branch master von origin.
    # nun https://github.com/gerdkolano/eutschlandfun
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ pushd /zoe-home/zoe-hanno/android/Deutschlandfunk/favoriten/src/
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git status | cat
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git commit -a
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git push -u origin master
    # Nun ändert jemand anderes. z.B. wird im Browser ein README.md hinzugefügt.
    # Dann muss folgendes Kommando gegeben werden
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git pull origin master
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ vim README.md
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git commit -a
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ git push -u origin master
    hanno@zoe:/zoe-home/zoe-hanno/android/Deutschlandfunk$ 
    # Die Zieladresse ist in .git/config gespeichert
    
