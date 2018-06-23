## Rechnerarchitektur-Aspekt
### bei Microsoftbetriebssystemen gibt es DLL die im Kernel- oder im User-Mode laufen. Warum ist eine DLL die im Kernel-Mode betrieben wird, das grössere Problem? Wie versucht Microsoft dieses Problem zu adressieren?
Eine DLL die im Kernel mode betrieben wird, kann dazu führen das das OS abstürtz, da ein Fehler im Kernelmode zu einem Absturz des Betriebssystem führt. Zudem kann die DLL auf verschiedene Resourcen ohne probleme zugreifen (zu viel erlaubniss). Schlimm sind Treiber, daher muss der Treiber signiert sein.
Die Windows Hardware Quality Labs (WHQL) sind eine Einrichtung von Microsoft zur Zertifizierung von Gerätetreibern und Komplettsystemen. Zur Zertifizierung testet ein Gerätehersteller sein Produkt oder seinen Gerätetreiber nach Vorgaben von Microsoft und reicht anschließend das Testprotokoll ein. Gegebenenfalls werden dann von Microsoft noch weitere Tests durchgeführt. Wenn Test bestanden erhalten Hersteller eine Signatur plus logo. :)

### CPU’s unterstützen 4 Ringe, die meisten Betriebssystem benutzen aber nur Ring 0 und Ring 3. Erklären sie den Zweck dieser Ringe (Kernel-Mode/User-Mode).
Zugrifsbereich definierten.
Wer darf wen unterbrechen, also nur ein niedrigerer Ring darf einen höheren unterbrechen. (Darum wurde für Virtualisierung ein weiterer Ring eingeführt der -1 ist HyperV)

### Wird das Memory Management bei Betriebssystemen (Abbildung logischer auf physischer Speicher) im Kernel-Mode oder im User-Mode gemacht?
Kernel-Mode

## Access Control / Autorisierung
### Was verstehen Sie unter einer „Trusted Computing Base“?
Die Summe aller Komponenten die sicherheitsrelevant sind:
* Software
* Hardware
* Firmware
Die Kombination davon ist verantwortlich für die Gewährleistung der Security Policy

### Was sind die wesentlichen Unterschiede zwischen Discretionary Access Control und Mandatory Access Control?
DAC, da sagt der benutzer wer ein objekt barbeiten darf. MAC da sagt das System wer ein Objekt bearbeiten darf.

### In welchen Punkten unterscheidet sich Discretionary Access Control von Role based access Control?
RBAC definiert den Usern eine Rolle und die Berechtigungen werden nicht mehr für die User vergeben wie bei DAC sondern auf die Rolle. Also ich gebe Objekte für die Rolle XY frei nicht für den Benutzer Hans. Da hans jedoch die Rolle XY hat darf er das Objekt manipulieren/gebrauchen usw.

### Erklären Sie das Grundprinzip von Labeling Systemen? Kennen Sie konkrete Einsatzgebiete?
Ich label ein objekt mit der entsprächenden Klassifikation/Berechtigung und gebe die Kategorien bekannt.

### Wo wird Role based access control primär eingesetzt? Wie wird RBAC von Betriebssystemenunterstützt?
In grösseren Firmen.

## Authentisierung
### Was verstehen Sie unter einer Mehrfaktor-Authentisierung?
Der Benutzer kann sich über eine der Folgenden sachen Authentisieren:
* Wissen (Password)
* Besitz (z.B. Chipkarte)
* Körperliches Merkmal/Biometrie
eine Mehrfaktor-Authentisierung ist nun eine, welche mindestens 2 der oben genannten möglichkeiten kombiniert. (z.B Sim karte im Handy)

### Mit welchen Problemen ist bei einer Authentisierung mittels Passwort zu rechnen?
* kann dupliziert, verteilt, weitergegeben und verraten werden
* kann vergessen werden
* kann eventuell erraten werden
* die Preisgabe von Wissen kann kompromittiert werden

### Wie gelangen Passwörter in falsche Hände?
* Durch verraten an dritte
* Durch Bruteforce
* Durch öffentliche informationen (Geb Datum)
* Durch liegenlassen des PW auf dem Notebook
* Durch unverschlüsselte übermittlung des PW über das Netzwerk.
* usw.

### Wie wird sichergestellt, dass bei einer Authentisierung mit einem USB-Stecker der Stecker nicht kopiert werden kann?
Er könnte, sofern jegliche eigenschaft des USB-Steckers kopiert werden konnte. Dies beinhaltet:
* ID der Hardware
* Grösse des USB
* Anzahl Partitionen

Jedoch gibt es heute auch den gebrauch von TPM -> welche mithilfe der USB informationen den inhalt verifizieren können, da die Verschlüsselung die infos des USB benötigt.

### Wie funktioniert grundsätzlich eine Authentisierung mittels Smartcard? (Wichtigste Schritt, kryptologischer Hintergrund)
Auf der Smartcard wird ein Privatekey gespeichert, welcher für die verifikation der eigenen Person dient. Nun muss lediglich die Smartcard an den PC angeschlossen werden, entschlüsselt werden und die Verifikation kann beginnen.

### Welche biometrische Merkmale können für eine Authentisierung ausgenützt werden?
alles was den Menschen einmalig macht. z.B.
* Fingerprint
* Iris
* Retina
* Face
* Voice
* Typespeed
* Venenverlauf
* uvm.

### Mit welchen Problemen muss man bei der Authentisierung mittels Fingerprint rechnen
2% aller menschen besitzen keinen Fingerabdruck.
Weitere probleme sind Hygene, Narbenbildungen, Verbrennungen usw.
Der fingerabdruck ist einmalig. Das bedeutet, hat eine andere Person meinen Fingerabdruck und kann ihn fälschen so kann ich nicht einen neuen Fingerabdruck erfinden. (daher gibt es erweiterungen, wie z.B. mit eingebauten Pulssensor)

### Was ist der Unterschied zwischen Enrollment und Verifikation bei der Biometrie?

Enrollment -> Aufnahme der Biometrieschen daten ins System (nur Feature werden gespeichert nicht die Sensor daten)
Verification -> überprüfung ob genug Features wiedergefunden werden konnten um Ja oder Nein zum zugriff zu sagen.
Die Merkmalsextrahierungen für Identifikation und Enrollment unterscheiden sich in der Regel nur durch die Parametrisierung (für das Enrollment sind höhere Bildqualitätsanforderungen zu erfüllen.

### Warum wird bei einem Fingerprint-Leser meistens das Template und nicht das Bild abgespeichert?
Würde das Bild abgespeichert werden müssten jedes mal wieder die Features herausberechnet werden -> dauert länger.

### Es gibt Anwendungen (z.B. biometrischer Pass) bei dem ein Foto des Fingerprints abgespeichert wird und nicht das Template. Warum?
Da jedes Land eine eigene implementierung der herauszulesenden Features hat, muss für jedes land aus dem Bild die Features extrahiert werden um sie mit der Lokalen person zu vergleichen. Leider konnten sich die Länder nicht auf ein Feature extraktionsalgorithmus entscheiden :(

### Bei biometrischen Systemen spricht man mit „False rejection rate“ und „False acceptance rate“? Es wäre nahe liegend die Empfindlichkeit des Systems so einzustellen dass FRR=FAR ist. Dies wird aber meistens nicht so gemacht. Warum?
Mit einem FR erhält man ein convenience-Problem, weil eine berechtigte Person nicht arbeiten kann also wird FRR minimiert, was zu einer erhöhung der FAR führt.

### Welche Anforderungen an biometrische Merkmale kennen Sie? Falls möglich, geben sie ein biometrisches Verfahren an, wo diese Anforderungen schwierig zu erfüllen sind.
Für biometrische Identifikation besonders gut geeignete biometrische Merkmale zeichnen sich dadurch aus, dass:

* sie möglichst einmalig sind, d. h. sich bei keiner weiteren Person exakt wiederholen: Einmaligkeit
* sie bei möglichst vielen Personen vorkommen: Universalität
* sie sich zeitlich möglichst wenig verändern: Konstanz
* sie mit möglichst einfachen technischen Mitteln erfassbar sind: Messbarkeit
* ihre Erfassung für den Anwender bequem durchführbar ist: Anwenderfreundlichkeit

Anforderungen sind:

* Universalität
  * Jede Person besitzt das Merkmal
* Eindeutigkeit
  * Das Merkmal ist für jeder Person verschieden
* Beständigkeit
  * Das Merkmal ist unveränderlich
* Quantitative Erfassbarkeit
  * Das Merkmal lässt sich mittels Sensoren quantitativ erfassen
* Performanz
  * Die Erfassung des Merkmals kann genau erfolgen und der Vorgang ist performant auszuführen
* Akzeptanz
  * Die Verwendung des Merkmals wird vom Benutzer akzeptiert
* Fälschungssicherheit
  * Das Merkmal ist fälschungssiche

### Was ist der Unterschied zwischen statischen und dynamischen biometrischen Methoden?
* Statische Merkmale
  * sind anatomische Merkmale des Körpers, die sich im Laufe des Lebens nicht oder kaum verändern (Fingerabdrücke, Iris, genetische Information, etc.).
* Dynamische Merkmale
  * sind Verhaltensmerkmale eines Menschen (Handschrift, Gangart, Stimme, etc.).
