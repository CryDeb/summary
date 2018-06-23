# Fragen Portmann
## Technische IT Sicherheit
### Übersicht über die Problemfelder der technischen IT - Sicherheit bekommen
TODO

### Welches sind die Schutzziele in der IT-Security? (CIA)
* Vertraulichtkeit
  * **confidentiality:** ensuring that information is accessible only to those authorized to have access
* Integrität
  * **integrity:** Safeguarding the accuracy and completeness of information and processing methods
* Verfügbarkeit
  * **availability:** ensuring that authorized users have access to information and associated assets when required.
* Weitere Unterteilung der Schutzziele bei Bedarf:
  * Authentizität
  * Verbindlichkeit
  * Nachvollziehbarkeit
  * Anonymisierung, Pseudomisierung

### Mit welchen technischen Massnahmen können die Ziele bei der Geheimhaltung erreicht werden?
Informationen dürfen nur Personen zugänglich sein, die dazu berechtigt sind.
 * Authentisierung
 * Zugriffsschutz
   * Files, Directories
   * Datenbanken
   * Kommunikationsverbindungen
 * Verschlüsselung
 * Überwachung (Auditing)
 * Physische Einrichtungen (z.B: Schlösser)

### Mit welchen technischen Massnahmen können die Ziele der Integrität erreicht werden?
Die Integrität stellt sicher, dass die Daten und Programme ihre Gültigkeit behalten.
* Authentisierungsmechanismen
* Zugriffsschutz
* Sichere Software
* Einsatz von Transaktionssystemen
* kryptologische Methoden (Message digest)

### Durch welche Ereignisse kann die Verfügbarkeit bedroht werden? Und mit welchen Massnahmen kann die Verfügbarkeit erhöht werden?
Eine sichere IT-Infrastruktur ist bei Bedarf verfügbar
* Hardwareausfall -> redundante Komponenten
* Softwareausfall -> redundante Services
* Denial of Service Attacken -> Firewall
* Viren -> Virenscanner
* Hacker -> Intrusion Detection
* Performance-Probleme -> Überwachungssoftware

## Was sind gemäss dem behandelten Melani-Halbjahresbericht die grössten Bedrohungen für schweizerische Firmen?
* DDOS
* Ransomware-Angriffe
* Defacements
* Drive-By
* Social Engineering und Phising
* Crimeware

### Was sind die wesentlichen Merkmale eines trojanischen Pferdes?
Ein Trojaner ist kein Virus, sondern ein Schadprogramm, das wie eine echte Anwendung aussieht. Im Gegensatz zu Viren replizieren sich Trojaner nicht selbst, können jedoch ebenso großen Schaden anrichten. Trojaner öffnen zudem eine Hintertür auf Ihrem Computer, über die bösartige Benutzer oder Programme Zugang zu Ihrem System erhalten und vertrauliche oder persönliche Informationen stehlen können.

### Welches sind die „Einsatzgebiete“ von BOT-Netzwerken?
* Versenden von Spam-Mails / Phisihng Mails
* Gebrauch als Proxy über den Zombie (identität verschleiern)
* Ausführen von DDOS Attacken
* Ausführen von Klickbetrug (klick auf werbung)

### Wie minimieren Sie in einer Firma die Bedrohung die von eigenen Mitarbeitern ausgeht?
* Gute Evaluation der Personen
* Ausschliesslich «Named Administratoren» zulassen
* Detailliertes Logging aller Administrationsarbeiten
* Steuerung der Arbeiten mit Change-Management-System
* Keine Entwickler auf produktiven Rechnern
* Einsatz von Jump-Hosts
* Schulungen
* Nur rechte welche wirklich benötigt werden.

### Wieso können Freelancer in einer Firma ein Problem sein (Sicherheitstechnisch)?
* Sie haben meist zugriff auf Teile der IT-Infrastruktur
* Fremde Leute sind schwieriger zu kontrollieren
* Firmenstandards können kaum durchgesetzt werden
* Besondere vertragliche Abmachungen sind notwendig

### Was sind mögliche Motivationen von Hackern?
* Geld
* Macht -> (Regierungen, Firmen)
* Spass
* Proof of Work

### Warum sind Script Kiddies eher eine abnehmende Gefahr?
Das hacken wird Professionalisiert, das bedeutet es Stecken neu Firmen/Regierungen hinter den grossen Hacking angriffen. Diese Firmen suchen Zero Day Vulnerabilities. Ein Skript kiddie hat meist keinen zugriff auf solche Zero Day Vulnerabilities und daher lassen sich die Systeme gegen Skript kiddies patchen.

### Was ist das Gefährliche bei professionellen Hackern?
* Grössere Resourcen der professionellen hackern -> können grösseren schaden anrichten.

### Schützt ein guter Virenschutz ausreichend vor trojanischen Pferden, die von professionellen Organisationen in Firmen eingeschleust werden?
Nein, ein virenschutz nütz lediglich gegen bekannte verhaltensweisen von Vieren. Wenn diese jedoch Professionel hergestellt werden, werden diese so konzipiert, dass sie den Vierenscannern nicht auffallen.


### Warum ist die physische Sicherheit bei Rechenzentren wichtig? (Ist die Gefahr von Bränden überhaupt vorhanden? Starke Erdbeben sind sehr selten: warum wird häufig in RZ ein besonderer Erdbebenschutz eingebaut?)
Sie ist wichtig, da sonst CIA verletzt werden würde.
Ein brand in einem RZ kann zum verlusst des Gesammten RZ führen. Dies wäre ein doppelter schaden. Die Hardwäre wäre komplett zu ersetzten sowie die Daten es wäre viel zu Teuer die absicherung nicht zu machen.
In der Schweiz gibt es 1000 bis 1500 Erdbeben im Jahr, davon fallen ca. 25 über einer Magnitude von 2.5 aus es ist also abwegig zu denken es gibt nie erdbeben in der Schweiz. Alle 50 bis 100 Jahre gibt es gar eins, dass grösser 6 ist. Man ist also gut geraten, die RZ gegen Erdbeben zu schützen.


### Mit welchen Massnahmen kann man Hardwareausfällen vorbeugen?
Redundanz

### Welches sind neuere Bedrohungen, die erst in den letzten Monaten aktuell wurden?
Heute über präparierte Web-Seiten oder ähnliche Methode

### Wie unterscheidet sich heutige Malware mit Malware, die vor 10 Jahren in Umlauf gesetzt wurden?
Sie werden immer Professioneller und aufwendiger.
