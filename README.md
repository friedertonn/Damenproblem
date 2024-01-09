# Damenproblem
Das Damenproblem ist eine schachmathematische Aufgabe. Auf einem Schachbrett mit n * n Feldern sollen
insgesamt n Damen so aufgestellt werden, dass sie sich gegenseitig nicht schlagen können.
Eine umfassende Beschreibung ist auf der Wikipedia-Website zu finden:
[https://de.wikipedia.org/wiki/Damenproblem](https://de.wikipedia.org/wiki/Damenproblem)

![Schachbrett](https://github.com/friedertonn/Damenproblem/blob/main/Fotos/Wikipedia.gif?raw=true) Quelle: Wikipedia.org

Es gibt Variationen bezüglich der Größe des Spielfeldes und der Spielfiguren, z. B. den Einsatz von 
Super-Damen (Amazonen). Super-Damen dürfen wie Damen und Springer ziehen.

Für die Programmierung eignet sich der Backtracking-Algorithmus. Dabei wird die Aufgabe als Baumstruktur
formuliert und nach der *trial and error* - Methode durchlaufen. Wenn in einem Zweig keine
Lösung möglich ist, wird jeweils bis zu dem Knoten zurückgegangen, der die weitere Lösungssuche ermöglicht.

Das Damenproblem wurde in Z80-Assembler programmiert. Die Vorlage bildete eine Programmierung von
Henrik Haftmann für den KC85:
[https://www-user.tu-chemnitz.de/~heha/hsn/kcemu/](https://www-user.tu-chemnitz.de/~heha/hsn/kcemu/)

Die Datei DAMEN.MAC enthält den Assemblercode. Über eine bedingte Anweisung in Zeile 15 kann der
Code sowohl für CP/M-Systeme als auch für den AC1-Monitor assembliert werden.
Die Binärdatei selbst belegt 1,5 KByte Speicherplatz und lässt sich auf dem AC1 mit 2 KByte Hauptspeicher
(von 1800h bis 1FFFh) ausgeführen.

![Hardcopy](https://github.com/friedertonn/Damenproblem/blob/main/Fotos/Superdamen_AC1.gif?raw=true)

Wenn in dem Rechner eine GIDE-Karte mit *real-time clock* RTC72421 eingesetzt ist, wird die Uhrzeit (mm:ss)
bei Start und Ende der Berechnung erfasst und die Differenzzeit auf dem Bildschirm angezeigt.
Die I/O-Adresse des RTC-Chips ist aktuell auf 85h eingestellt. Eine Änderung im Quellcode ist möglich.

Das Assemblieren des Quellcodes kann mit dem Macroassembler M80.COM erfolgen:
```
M80 = DAMEN/L
```

Zum Linken des Programmcodes wird der Linker LINKMT.COM empfohlen:
```
LINKMT DAMEN
```

Der Programmcode befindet sich dann in der Datei DAMEN.COM.
Das Assemblerlisting steht in der Datei DAMEN.PRN.
