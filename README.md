# Damenproblem
Das Damenproblem ist eine schachmathematische Aufgabe.
Eine umfassende Beschreibung ist auf Wikipedia.org zu finden:
[https://de.wikipedia.org/wiki/Damenproblem](https://de.wikipedia.org/wiki/Damenproblem)

Die Datei DAMEN.MAC enthält den Assemblercode für CP/M und den AC1-Monitor.
Am Anfang des Assemblercodes wird definiert, für welches System die Binärdatei gebildet werden soll.

![](https://www.ftonn.de/GIT-Projekte/Damenproblem/Superdamen_AC1.gif)

Zum Assemblieren kann der Macroassembler M80.COM verwendet werden.

M80 = DAMEN/L

Das Linken des Programmcodes erfolgt mit dem Linker LINKMT.COM

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

