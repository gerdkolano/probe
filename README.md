probe
=====
trying to find out how to use github Wie krieg' ich nun meine Dateien hier rein?

Das in https://github.com/gerdkolano/probe/edit/master/README.md getippte

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

