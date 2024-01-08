# cron_fritzbox-reboot - FRITZ!Box Neustart Skript - jede Nacht, einmal die Woche, wie ihr wollt

## Quick 'n Dirty Scripting | nicht schön, aber selten

![avm-fritzbox_pressekit.png](avm-fritzbox_pressekit.png?raw=true "avm-fritzbox_pressekit.png")

Bei diesem Skript handelt es sich um ein klassisches Linux Bash-Skript, welches ich verwende um jeden Freitag, um 4:50, meine 3 AVM FRITZ! Geräte neuzustarten - eine FRITZ!Box und zwei FRITZ!Repeater. Es sollte ab FritzOS 6.0 (2013) funktioneren - also auch für die 6.8x und 6.9x. Dieses Bash-Skript nutzt das Protokoll TR-064 nicht die WEBCM-Schnittstelle. :+1:

Folgende Variablen müssen angepasst werden:

| Variable | Erklärung |
|---|---|
| `IPS` | IP-Adressen der AVM FRITZ! Geräte. Können mehrere sein, alle Geräte müssen aber das gleiche Passwort haben. |
| `FRITZUSER` | Username der FRITZ! Weboberfläche. Es empfiehlt sich einen dedizierten `restart`-Benutzer anzulegen. In einigen Fällen kann hier `root` eingetragen werden, wenn kein Username zum Login notwendig ist. |
| `FRITZPW` | Passwort der FRITZ! Weboberfläche. |

Viel Spaß!

## Weitere Infos zu TR-064 
* http://fritz.box:49000/tr64desc.xml
* https://wiki.fhem.de/wiki/FRITZBOX#TR-064
* https://avm.de/service/schnittstellen/

## Beispiele

### Crontab

[Wiki-Artikel](https://wiki.ubuntuusers.de/Cron/) zur Crontab auf ubuntuusers.de

`vi /etc/crontab`

```
# FRITZ! Geräte neustarten
50 4 * * 5 root /root/Scripts/cron_fritzbox-reboot.sh
```

### Terminal / Bash

Natürlich kann man das Skript auch einfach manuell über die Bash / den Terminal jederzeit auführen.

Beispiel: `./cron_fritzbox-reboot.sh`

## Inspiration & Dank

 * [Dragonfly](https://homematic-forum.de/forum/viewtopic.php?t=27994)

## Lizenz

Copyright 2024 Nico Hartung. Released under the MIT License.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
