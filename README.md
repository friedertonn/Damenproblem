# Damenproblem
Das Damenproblem ist eine schachmathematische Aufgabe. Auf einem Schachbrett mit n * n Feldern sollen
insgesamt n Damen so aufgestellt werden, dass sie sich gegenseitig nicht schlagen können.
Eine umfassende Beschreibung ist auf der Wikipedia-Website zu finden:
[https://de.wikipedia.org/wiki/Damenproblem](https://de.wikipedia.org/wiki/Damenproblem)

![](https://www.ftonn.de/GIT-Projekte/Damenproblem/Wikipedia.gif) Quelle: Wikipedia.org

Es gibt Variationen bezüglich der Größe des Spielfeldes und der Spielfiguren, z. B. den Einsatz von 
Super-Damen (Amazonen). Super-Damen dürfen wie Damen und Springer ziehen.

Für die Programmierung bietet sich der Backtracking-Algorithmus an. Dabei wird die Aufgabe als Baumstruktur
formuliert und nach der *trial and error* - Methode durchlaufen. Wenn in einem Zweig keine
Lösung möglich ist, wird jeweils bis zu dem Knoten zurückgegangen, der eine weitere Lösungssuche ermöglicht.

Das Damenproblem wurde in Z80-Assembler programmiert. Die Vorlage bildete eine Programmierung für den KC85:
[https://www-user.tu-chemnitz.de/~heha/hsn/kcemu/](https://www-user.tu-chemnitz.de/~heha/hsn/kcemu/)

Die Datei DAMEN.MAC enthält den Assemblercode. Über eine bedingte Anweisung am Anfang der Datei kann der
Code sowohl für CP/M-Systeme als auch für den AC1-Monitor assembliert werden.
Die Binärdatei selbst belegt nur 1,5 KByte Speicherplatz und kann auch auf dem AC1 mit 2 KByte Hauptspeicher
(von 1800h bis 1FFFh) ausgeführt werden.

![](https://www.ftonn.de/GIT-Projekte/Damenproblem/Superdamen_AC1.gif)

Wenn in dem Rechner eine GIDE-Karte mit RTC-Chip eingesetzt ist, wird die Uhrzeit (mm:ss) bei Start und Ende 
der Berechnung erfasst und die Differenzzeit auf dem Bildschirm angezeigt.
Die I/O-Adresse des RTC72421-Chips ist aktuell auf 85h eingestellt. Eine Änderung im Quellcode ist möglich.

Das Assemblieren des Quellcodes kann mit dem Macroassembler M80.COM erfolgen:

M80 = DAMEN/L

Zum Linken des Programmcodes wird der Linker LINKMT.COM empfohlen:

LINKMT DAMEN

Der Programmcode befindet sich dann in der Datei DAMEN.COM.
Das Assemblerlisting steht in der Datei DAMEN.PRN.

**Wichtiger Hinweis:** Beim Hochladen der Dateien auf GITHUB wurden die Zeilenumbrüche in den Textdateien 
von 0Dh, 0Ah (CPM-Notation) auf 0Ah (UNIX-Notation) geändert. Dies hat zur Folge, dass der M80-Assembler 
die Bearbeitung mit der Meldung *%No END statement* abbricht. Unter CP/M gibt es das Programm UNIX2CPM.COM,
welches die ursprünglichen Zeilenumbrüche 0Dh, 0Ah wieder herstellt.

UNIX2CPM DAMEN.MAC

Das Programm UNIX2CPM.COM ist z. B. auf folgender Website zu finden: 
[http://www.znode51.de/cpmtools/](http://www.znode51.de/cpmtools/)
