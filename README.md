# Ansible pull deployment repo

## tldr:
In diesem Repo wird meine Infrastruktur als code abgebildet.
Server, Workstations und whatever sollen durch einen einfachen befehl auf den definierten stand gebracht werden.

Magische Formel:
```Bash
ansible-pull https://github.com/Peppeppa/ansible_dev.github
```

## Voraussetzungen:
Git und ansible muss installiert sein.
Die einzurichtende Maschine muss in der hosts datei mit seiner ip vermerkt sein.
Die IP/Domain muss in die zu verwendende kategorie eingetragen werden. es muss eine ssh verindung zu github bestehen,.

## Funktionsweise:
Die local.yml updated im ersten zug die paket repos.
Danach die Base role, welche auf jeder Maschine gespielt wird.

 ### Base role
 Checkt ob die User medvidec, root und angela vorhanden und richtig konfiguriert sind.
Bereitet die ansible umgebung vor.
Installiert die erste Software. Weitere kannn in packages_utility.yml hinzugefügt werden.
Richtet Systemdienste wie clock, cron, ssh oder locale ein.


Daraufhin folgt die Einrichtung der vorher definierten Kategorie (Workstation, Server...)

### dev 

Die Dev Kategorie richtet mein git working direktory ein.
Ein kleiner zentraler server der nur meinen git code hostet.
Wenn ich darauf arbeiten möchte muss ich mich egal von welchem gerät nur per ssh aufschalten und habe meinen code zentral verwaltet.
Hautpsoftware sind Tmux und Nvim.
Er verfügt des weiteren über einen data ordner, welches ein Smb share vom NAS ist.


# ansible-pull
