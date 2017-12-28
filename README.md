# FRITZ!Box Neustart Skript - jede Nacht, einmal die Woche, wie ihr wollt

#### Quick 'n Dirty Scripting | nicht schön, aber selten

![avm-fritzbox_pressekit.png](avm-fritzbox_pressekit.png?raw=true "avm-fritzbox_pressekit.png")

Bei diesem Skript handelt es sich um ein klassisches Linux Bash-Skript, welches ich verwende um jeden Freitag, um 4:50, meine 3 AVM FRITZ! Geräte neuzustarten - eine FRITZ!Box und zwei FRITZ!Repeater.

Folgende Variablen müssen angepasst werden:

 * `IPS` - IP-Adressen der AVM FRITZ! Geräte, können mehrere sein 
 * `FRITZUSER` - Username der FRITZ! Weboberfläche, kann leer gelassen werden, wenn man nur ein Passwort eingeben muss
 * `FRITZPW` - Passwort der FRITZ! Weboberfläche, muss bei allen FRITZ! Geräten gleich sein

Viel Spaß!

#### Beispiel

##### Crontab

[Wiki-Artikel](https://wiki.ubuntuusers.de/Cron/) zur Crontab auf ubuntuusers.de

`vi /etc/crontab`

```
# FRITZ! Geräte neustarten
50 4 * * 5 root /root/Scripts/cron_fritzbox-reboot.sh
```

##### Terminal / Bash

Natürlich kann man das Skript auch einfach manuell über die Bash / den Terminal jederzeit auführen.

Beispiel: `./cron_fritzbox-reboot.sh`

#### Inspiration & Dank

 * [Dragonfly](https://homematic-forum.de/forum/viewtopic.php?t=27994)
