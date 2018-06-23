## Einsatzbereiche Unix / Windows
### Zählen Sie typische Einsatzbereiche von Unix-Server auf und begründen Sie ihre Antwort
* Desktop -> nicht häufig linux /immer mehr MacOS
* Fileserver -> nicht häufig da Windows Clients
* Datenbank-Server -> häufig
* Applikationsserver -> häufig
* Mail-Server -> nicht häufig
* Kommunikationsserver -> häufig
* Webserver -> sehr häufig
* IoT -> sehr häufig
* Netzwerkdienste (z.B. DNS) -> weniger häufig
* Authentisierungsserver -> nicht häufig

### Zählen Sie typische Einsatzbereiche von Microsoft-Betriebssystemen auf und begründen Sie ihre Antwort.
* Desktop -> häufig da jemend zu blamen ist
* Fileserver -> häufig da Windows Clients
* Datenbank-Server -> weniger häufig
* Applikationsserver -> weniger häufig
* Mail-Server -> häufig (Exchange)
* Kommunikationsserver -> häufig
* Webserver -> weniger häufig
* IoT -> weniger häufig da nicht quelloffen und anpassbar
* Netzwerkdienste (z.B. DNS) -> häufiger da häuffig schon windows clients
* Authentisierungsserver -> häufig

### Die grundlegenden Sicherheitskonstrukte von Unix wurden ca. 20 Jahre vor den entsprechenden Konstrukten der aktuellen Microsoft-Betriebssysteme definiert. Was sind die Konsequenzen davon?


## Sicherheitsmechanismen Unix / Windows
### Neben funktionalen Vorteilen hat das „shared Memory“-Konzept auch wichtige Sicherheitsfunktionen. Was wird im Bereich der Sicherheit von shared Memory sichergestellt?
Shared memory bedeutet, dass alle Processe den gleichen Memory gebrauchen. Damit nun jedoch jeder process nur sein eigenes anfasst, stellt das Betriebssystem dem Process einen virtuellen adressraum zur verfügung.

### Interne wird der Unix-Benutzer auf eine 16-Bit Zahl abgebildet. Bei Microsoft-Betriebssystemen ist es eine komplex aufgebaute SID (Security Identifier). Was sind die Konsequenzen daraus?
SID sind global eindeutig. Es gibt in Windows Netzwerken keine 2gleichen SIDs, bei UNIX systemen kann es hingegen sein, da es lediglich ein mapping auf eine 16Bit zahl ist. Dies bedeutet, dass bei UNIX systemen 2 Systeme die gleichen Nummbern für unterschiedliche zwecke verwenden können.

### Zählen Sie einige wichtige Unterschiede zwischen den Gruppenkonzepte von Unix und Microsoft auf?
TODO

### Wie können im Unix-Umfeld Zugriffsberechtigungen vergeben werden?
Unix vergibt die Berechtigungen auf Dateiebene. Dabei wird bei der Datei festgelegt wem sie gehört (Eigentümer), welcher gruppe sie "gehört" (Gruppe) und wer was machen darf. Dazu kriegt die Datei einen eigentümer (1. Partei), eine Gruppe (2. Partei) und alle anderen (3. Partei). Nun kann für die jeweilige Partei die berechtigung festgelegt werden. (siehe befehl chmod 777 <<Dateiname>>)

### Moderne Unix-Betriebssysteme unterstützen auch Access Control Listen (ACL’s). Warum werden diese selten verwendet und was ist bei einem geplanten Einsatz von ACL’s zu beachten?
TODO

### Bei Unix gibt es das Konstrukt des SUID-Bit, das häufig missbraucht wird. Was passiert, wenn bei einer Datei dieses Zugriffsbit gesetzt ist? Wie könnte ein typischer Missbrauch aussehen?
In simple words users will get file owner’s permissions as well as owner UID and GID when executing a file/program/command.
Statt das ich every one else definiere könnte ich auf eine datei einfach das SUID setzen was jedoch nicht die intention hinter dieser idee ist.

### Bei grösseren Umgebungen ist es notwendig, dass man die Benutzerverwaltung zentralisiert. Welche Methoden sind in Unix-Umgebungen möglich?
* Einbindung in eine AD
* Gebrauch von OpenLDAP
* MIT Kerberos
* Heimdal
* uvm.

### Wie wird im Microsoft-Umfeld eine zentrale Benutzerverwaltung implementiert?
Es wird ein AD Server gebraucht, welche eine LDAP komponente besitzt und ein Kereberos Protokoll.

### Microsoft verwendet für die Authentisierung in Netzwerkumgebungen das Protokoll Kerberos. Was sind wesentliche Vorteile dieses Protokolls? (Prüfungsrelevant sind auch die Fragen des Arbeitspapiers zu Kerberos)
TODO

### Braucht der Client das Passwort noch?
Nein

### Gehen irgendwelche Passwörter oder Hashwerte über das Netzwerk?
Jein es gehen verschlüsselte Keys über das Netzwerkt, welche als authentification dienen.

### Warum wird ein Timestamp verwendet?

### Kann der Client das TGS entschlüsseln?
TGS ist offiziel (gemäs mit doku) eigentlich nur der Servic also nein er kann keinen service entschlüsseln.

### Findet eine Kommunikation zwischen KDC und dem Server Bob statt?
nein nur der Authentication server sowie das Ticket Granting Service haben zugriff auf das KDC

### Wird für Kerberos asymetrische Kryptographie benötigt?
nein nur eine symetrische.

### Was wird mit dem Konstrukt Windows Integrity Control angestrebt?
The Windows integrity mechanism enables a number of important scenarios in Windows Vista. In order to address the requirements, the Windows integrity mechanism's design had to meet the following goals.

* Integrity levels must be assigned automatically to every security access token during access token creation, so that every process and thread has an effective integrity level for access control.
* The security subsystem automatically assigns mandatory labels to specific object types.
* The system must use as few integrity levels as possible, to keep the basic architecture simple to understand and use.
* Integrity policy must be flexible to meet the access requirements of different object resource managers, and to allow for future extensibility.
* Integrity mechanism must integrate with existing security architecture to minimize impact to the large legacy of system and application code that depends on Windows security.
* There is no requirement for administrators or users to configure integrity levels for the enforcement mechanism to work correctly.

### Inwiefern sind Linux-Systeme mit aktiviertem SELinux sicherer als Linux-Systeme ohne diese Erweiterung?
TODO

### Warum ist eine Überwachung (Monitoring) von Unix-und Microsoft-Servern in einem professionellen Umfeld wichtig?
TODO

## Laborübung Windows Rechner
### Für die Laborübung wurde ein eigenes AD SECLAB aufgebaut. Für dieses AD wurde ein einseitiger Trust zum AD des Enterprise Lab aufgebaut. Was wurde damit erreicht?
TODO

### Was kann mit einer AD-Delegation erreicht werden?
TODO

### Warum schlug der Versuch fehl, direkt vom Client-Rechner aus, diesen Rechner in das AD aufzunehmen?
TODO

### Zählen sie einige Berechtigungen auf, die sie delegieren können.
TODO

### Was verstehen Sie unter einem mehrstufigen Gruppenberechtigungskonzept?
TODO

### Wie funktioniert die Vererbung der Berechtigung bei verschachtelten Ordnern?
TODO

### Was kann mit GPO’s (Gruppenrichtlinien) erreicht werden?
TODO

### Wie können sie Microsoft Client-und Server-Rechner härten?
TODO

### Wie können sie erreichen, dass Clients in verschiedenen Anwendungsgebieten unterschiedlichgehärtet werden (z.B. Kiosk-Rechner in der Mensa , Clientrechner in der Forschung, Clientrechner in der Finanzabteilung)
TODO

### Was kann mit WIC erreicht werden?
TODO

### Erklären sie die Funktionsweise von WIC?
TODO

## Laborübung Linux-Rechner
### Warum ist das Passwort bei Linux nicht mehr in der Datei /etc/passwd, sondern in der Datei /etc/shadow?
Die Deite /etc/passwd wurde das SUIDBit gesetzt, konnte also vom Benutzer selber gelesen werden. so konnte ein einfaches skritp (nur schon eine webseite) das Passwort zu brutforcen das wurde mit der neuen Datei /etc/shadow verbessert.

Bei früheren Versionen von Linux speicherte man die die Passwörter direkt in die passwd-Datei. Allerdings war dies durch einen sogenannten Wörterbuchangriff und der beispielsweise mit Hilfe des Programmes crypt möglich, diese Passwörter in vielen Fällen zu entschlüsseln und auszulesen.

### Wie funktionieren die Standard Zugriffsberechtigungen unter Linux (Unix)

### Was kann mit sudo erreicht werden? Warum wird mit sudo gearbeitet?
mit sudo erhalte ich temporäre root rechte für den auszuführenden befehl.
Es ermöglicht mir ein arbeiten, ohne dass ich root bin (wie es häufig bei windows der fall ist)

### Was ist bei der Kerberos Authentisierung der Unterschied zwischen dem TGT und dem TGS?
TGT -> Ticket Granting Ticket
TGS -> Nur der Server

### Wie funktioniert die Authentisierung mit Kerberos (nur Übersicht)?
\begin{figure}[H]
    \centering
    \includegraphics[width=1\textwidth]{images/02C-Kerberos_overview.png}
\end{figure}

### Was konnten sie mit der Kerberos-Authentisierung erreichen?
Kerberos is a computer network authentication protocol that works on the basis of tickets to allow nodes communicating over a non-secure network to prove their identity to one another in a secure manner.

### Kann die Kerberos-Authentisierung für jeden Anwendungsfall (von Authentisierung) unter Linux verwendet werden? Was muss gewährleistet sein?
Das selbe verschlüsselungsprotokol muss verwendet werden.

### Warum ist beim Einsatz von Samba die Verwendung von ACL’s und von Kerberos sinnvoll?
???
