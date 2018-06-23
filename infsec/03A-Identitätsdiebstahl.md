# Fragen Puly
## Identitätsdiebstahl
### Nach welchen Kriterien lassen sich Hacker und ihre Opfer klassifizieren?
**Hacker**
* Hacktivisten
* Cyberterroristen
* Staatliche Organisationen
* Skript Kiddies
* Organisiertes Verbrechen
* Wissenschaftler / Krypto-Analytiker

**Opfer**
* Einzelpersonen (gezielt)
* Einzelpersonen (zufällig)
* Die grosse Masse (zufällig)
* Organisationen / Firmen (gezielt)

### Welche Angriffsstrategien werden typischerweise gegen welche Opfer eingesetzt?
* Einzelpersonen (gezielt)
  * Identitätsdiebstahl
  * Informationsdiebstahl
  * Diskreditierung (vgl. Fall Hildebrand, Zuppiger)
* Einzelpersonen (zufällig)
  * z.B. Phishing und Skimming Attacken auf Bankomatkunden
* Die grosse Masse (zufällig)
  * z.B. Viren-Angriffe auf gewisse Betriebssysteme
* Organisationen / Firmen (gezielt)
  * z.B. DDoS Angriffe gegen Firmen

### Beschreiben Sie zwei unterschiedliche Geschäftsmodelle von Hacker Organisationen.
* Erpressung
* DDoS as a Service

### Was versteht man unter Identitätsdiebstahl?
* Ein Hacker stielt das E-Mail Passwort seines Vorgesetzten.
* Ein Hacker stielt das Login Passwort zum PC eines Mitarbeiters.
* Ein Hacker stielt ein Facebook Passwort.

In den USA ist Identitätsdiebstahl ein grosses Problem, weil es dort – anders als in der Schweiz – mit der Sozialversicherungsnummer ein personenbezogenes Merkmal gibt, das hinreichend ist, um Steürn zurückzufordern und Kreditkartenverträge abzuschliessen. Allein 2011 belief sich der finanzielle Schaden infolge von Identitätsdiebstahl auf 3.6 Mrd. USD. NZZ, 20.01.2014

### Beschreiben Sie mögliche Konseqünzen von Identitätsdiebstahl für die Opfer.
* Finanzielle Folgen (Bestellungen auf meinen Namen etc)
* Rechtliche Folgen (Kinderpornografie etc)
* Gesellschaftliche Folgen (Postings von meinem FB Account)

### Analysieren Sie die Authentifikationsmethoden 1 – 4 auf Stärken und Schwächen.
1. Telnet and Remote Shell
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/03A-Telnet.png}
    \caption{Authentifizierung 1}
\end{figure}
2. Telnet and Remote Shell
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/03A-Mailinglist.png}
    \caption{Authentifizierung 2}
\end{figure}
3. Telnet and Remote Shell
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/03A-WindowsLogin.png}
    \caption{Authentifizierung 3}
\end{figure}
4. Telnet and Remote Shell
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/03A-UNIX_Login.png}
    \caption{Authentifizierung 4}
\end{figure}

### Wie schützen Betriebssysteme typischerweise unsere Identitäten, und wie kann dieser Schutz mit Maschinenzugriff ausgehebelt werden?
**Windows**
Windows Betriebssysteme (seit NT) speichern Passwortinformationen in der Registry Datei Security Account Manager (SAM). Windows Kernel sichert SAM, so dass Datei nicht kopiert werden kann.

**Linux/UNIX**
Unix Betriebssysteme (seit 1990) speichern Passwortinformationen in Shadow Dateien. Nur Superuser können diese Dateien lesen.


**Fazit**
* In Klartext gespeicherte (z.B. FileZilla) oder gecachte (z.B. WindowsDomänen Anmeldung) Passwörter können mit Maschinenzugriff leicht
geklaut werden.
* Betriebssysteme schützen Passwortdateien, jedoch kann der Schutz leicht
umgangen werden.
* Anwendungsprogramme und Betriebssysteme verschlüsseln Passwörter
bevor sie in einer Passwortdatei abgelegt werden.

### Welche Angriffsstrategien auf gestohlene Passwort-Hashs hat ein Hacker zur Verfügung?
1. Passwort-Hashfunktion knacken
2. Brute-Force Attacken
  * Alle möglichen Kombinationen werden systematisch durchprobiert
  * Jeder Kandidat wird verschlüsselt und in der Passwortdatei gesucht
  * Vorteil: knackt irgendwann jedes Passwort -¿ vollständige Methode
3. Wörterbuch Attacken
  * Nur Wörter aus einem vorgegebenen Wörterbuch werden durchprobiert
  * Beruht auf Annahme, dass sinnvolle Wörter als Passwort verwendet
wurden oder dass beim Passwort ein Algorithmus hinterlegt ist (z.B.
Palindrom)
  * Knackt nur Passwörter im Wörterbuch (unvollständige Methode)
4. Lookup Tabellen
  * Wörterbuch mit 1M Wörter verlangt 1M Hashberechnung
  * Effizienter sind Wörterbücher mit (Wort / Hashwert) Einträgen
  * Jetzt muss nur noch nach dem Hashwert gesucht werden
  * Trade-off: man investiert mehr Memory um Rechenzeit zu sparen.
  * Knackt nur Passwörter in der Tabelle (unvollständige Methode)


### Sie können den Aufwand von Brute-Force Attacken vorausberechnen.
Passwörter bestehen aus den Symbolen (A - Z, a - z, 0 - 9) und 8 zusätzlichen Sonderzeichen. Das Content Management System Joomla verschlüsselt Passwörter mit MD5. Wir verwendet die Software oclHashcat für einen BruteForce Angriff mit folgendem PC: 2x AMD HD 6990, 880 MHz GPU, 1250 MHz RAM, Catalyst 12.1, Windows 7 x64. Benchmark Tests ergaben 23083.9 M/s also rund 23 * 109 Hashs / s.

**Maximale Wartezeit für Passwörter der Länge 7:**
 ((70 7 ) s ) / (23 x ( 109 )) = 5,96 Minuten
**Maximale Wartezeit für Passwörter der Länge 9:**
 ((70 9 ) s ) / (23 x ( 109 )) = 20,30 Tage
**Maximale Wartezeit für Passwörter der Länge 11:**
 ((70 1 1) s ) / (23 x ( 109 )) = 272,43 Jahre


### Nennen Sie den Unterschied zwischen Wörterbücher und Lookup-Tabellen.
Lookup-Tabellen sind vorgefertigte Tabellen mit Hashwert + Klartext Passwort. Die Hashes sind alle bereits vorgerechnet. Man muss nun nur noch anhand des gewünschten Hashes das Passwort raus suchen. Ein Wörterbuch ist im Gegensatz dazu nur eine Sammlung möglicher Passwörter im Klartext. Zum Beispiel kann der Duden als Wörterbuch herhalten. Nachher wird beim Angriff jeder Hash zum Wort berechnet. Die Hashes sind somit beim Zeitpunkt des Angriffes nicht vorberechnet.

### Sie können die Funktionsweise von Rainbow-Tabellen anhand eines Beispiels erklären.
**Erklärung**
http://kestas.kuliukas.com/RainbowTables/

**Vorteile Nachteile von Rainbow Tabellen**
* Hybride Version von Lookup und Brute-Force
* Kompromiss bezüglich Hashberechnungen, Speicherplatz, Vollständigkeit
* Verschiedene Tabellen für verschiedene Hash-Algorithmen
* Knackt nur Passwörter im Wörterbuch (unvollständige Methode)
* Auf Passwörter einer fixen Länge spezialisiert

### Gegen welche Angriffe hilft Salz? Begründen Sie ihre Antwort ausführlich.
**Angriffe**
Das Salzen eines Passwort hilft gegen Lookup und Rainbow Tables. Es hilft sobald eine Angriffmethode darauf basiert, dass sie klar Hash zu einem Text mappen kann. Also wenn diese vorberechnet sind. Dies ist bei Lookup Tables sowie bei Rainbow Tables der Fall. Die Hashes um diese Tables aufzubaün wurden ohne das Salt berechnet, somit ist es für das gegebene Passwort nicht mehr zu gebrauchen. Da das Salt bekannt ist, kann es bei Angriffen, welche die Hashes bei Laufzeit berechnen (Brute-Force) einfach angehängt werden. Der Brute-Force Algorhitmus muss, kann dies genau so machen, wie das Betriebssystem selbst. Es führt die Operation h(pwd . salt) vor dem Vergleich aus.

### Nennen Sie ein Betriebssystem, das Salz verwendet und eines, das kein Salz verwendet.
**Kein Salt:**
* Windows
**Salt:**
* Linux
* Mac OS X
* Solaris

### Definieren Sie eine Passwort-Policy für eine fiktive Firma und begründen Sie die von Ihnen verlangten Regeln in Bezug auf die verschiedenen Angriffsmethoden.
**Passwortlänge**
Eine mindestlänge von 10 Characters sollte vorgeschrieben sein. Dies verunmöglicht praktisch ein Brute-Force Angriff, welcher auf reinem ausprobieren von möglichen Kombinationen basiert.
**Passwortzeichen**
Ein Passwort muss mindestens ein Sonderzeichen, eine Nummer, sowie auch gross und klein Buchstaben enthalten. Dies verhindert, dass das Passwort mithilfe eines Wörterbuchs geknackt wird.
**Blacklist**
Mögliche schlechte Passwörter, wie Namen, Alter oder Firmennamen dürfen nicht verwendet werden. Es dürfen zum Beispiel auch keine Passwörter verwendet werden, welche allgemein als beliebte Passwörter bekannt sind. Dies hilft auch gegen Wörterbuch Angriff, sowie auch gegen Lookup und Rainbow Tables.
**Passwortdaür**
Ich würde die maximale Passwortdaür nicht zu kurz wählen. Dadurch könnte zwar die Sicherheit theoretsch erhöht werden, da Hacker welche eine Passwort ergattern konnten, nicht beliebig lange Zugriff auf das System erhalten. Jedoch, hat eine Studie von Microsoft gezeigt, dass umso kürzer die Passwortdaür ist, die Mitarbeiter anfangen, die Passwörter aufzuschreiben, oder allgmein einfach kürzere Passwörter wählen. Somit geht der erhoffte Schutz natürlich verloren. Deshalb würde ich für sehr kritische Systeme eine Passwortdaür von 90 Tagen wählen. Nichtkritische Systeme bis zu 180 Tagen.

### Was ist ein Man-in-the-Middle (MITM) Angriff?
Bei einem Man in the Middle Angriff stellt sich der Angreifer zwischen Opfer und Server. Er fängt die Kommunikation des Opfers ab, manipuliert diese, und schickt sie weiter an den Server. Die Antworten leitet er manipuliert zurück an das Opfer. Somit wird dem Opfer vergegauklet er würde direkt mit dem Server kommunizieren, sowie dem Server, er hätte einen validen, sicheren User der ihn kontaktiert. Ein Man in the Middle Angriff ist aber nicht nur auf Software und Netzwerkkommunikation begrenzt. Wenn man an einem Bankautomat ein zusätzliches Tippfeld über das eigentliche Tippfeld baut, gilt dies auch als Man in the Middle Angriff.

### Nennen Sie je ein Beispiel von Hardware und Software MITM Attacken.
* Hardware Keylogger
* Skimming (Overlay Tastatur)
* Software Keylogger (Spyware)
* Akustische Keylogger (mit Richtmikrofon)
* Elektromagnetische Keylogger
* Optische Keylogger

### Zeichnen Sie einen Phishing-Angriff auf ein e-Banking System mit TAN Generator auf.
TAN => Bank Transaktionsnummer
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/03A-TAN.png}
    \caption{Man in the Middle obschon TAN}
\end{figure}


### Welche Vorteile hat ein TAN Generator gegenüber einer Streichliste?
Der TAN Generator generiert den Code sobald dieser Benötigt wird. Eine Streichliste kann somit einfacher gestohlen werden, da sie noch für X-belibige Operationen gebrauchbar ist. TAN Generatoren, welche nicht nur den Code verschicken, sondern auch eine zusätzliche Informationen, wie zum Beispiel den Betrag und der Empfänger, der kann Man in the middle Attacken verhindern. Sollte jemand eine Zahlung abgeben wollen, für den Betrag von 100 Chf an Person X und der TAN Generator meldet eine Zahlung von 100’000 Chf an Person Y, bricht man die Transaktion wohl ab und gibt den Bestätigungscode nicht im Browser ein. Somit erhält der Man in the middle den TAN Code zur Autorisierung der Zahlung nicht.

### Welche Risiken entstehen bei der Nutzung von mobile TAN über ein Smartphone?
* Der grosse Vorteil von TAN ist es, dass eine zweite Information über ein zweit Kanal benötigt wird um eine Transaktion abzuschliessen. Normaler- weise arbeitet man an einem Computer mit dem EBanking und erhält die TAN Nr auf das Handy. Wenn man nun aber mit dem Handy EBanking betreibt und auf dem selben Handy das Bestätigungssms erhält ist ein Man in the Middle Angriff wieder möglich.
* Betrüger können die HandyNr stehlen und SMS an diese umleiten. Die ganze mTAN Technologie ist an die Telephondaten gebunden.

### Wie könnte ein Phishing-Angriff mittels Pharming und einem Pineapple-Device aussehen.
**Pharming**
Pharming bezeichnet verschiedene Angriffe auf DNS Anfragen. Beispiel: Benutzer tippt e-finance.postfinance.ch im Browser. Statt der korrekten IP 194.41.166.132 erhält der Browser die IP einer Phishing Seite.

**Hacker Strategien:**
* Direkter Angriff auf DNS Server (schwierig)
* Einfacher: lokale Host-Datei (z.B. mit Malware) abändern
* Effektiver: Angriff auf lokalen Netzwerk Router
* Strategie: Verlockung über gratis WiFi (Honeypot) oder SSID <Public>

**Pineapple-Device**
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/03A-Pineapple.png}
    \caption{Pineapple device}
\end{figure}
Ein Pineapple bietet ein kostenloses Wlan an.  Ergänzent zu einem normalen Router ist das Pineapple fürs Hacking optimiert. Es kommt mit vorinstallierten Tools zum Beispiel für Man in the Middle Attacken.
**How-To**
Indem na das Wirless mithilfe des  Pineapple anbietet erhält man Kontrolle über das Netzwerk. Nun kann man ein DNS innerhalb des Netzwerks definieren. Somit muss man kein ”richtigen”DNS Server mehr angreifen. Dies erleichtert das ”Phramingërheblich. Nun kann man den Benutzer auf die gewünschte Pishing Seite umlenken.

### Erklären Sie SQL Injection Angriffe anhand eines Beispiels.
Angriff auf SQL Datenbanken mit speziell präparierten Benutzereingaben. Der
Angriff wird durch mangelnde Ueberprüfung (Programmierfehler) der Benutzereingabe ermöglicht.

### Mit welchen Verteidigungsmassnahmen können SQL Injection Angriffe erschwert werden?
Serverseitig muss die Eingabe überprüft werden. Mysql Datenbanktreiber bieten in der Regel ”Prepared Statementän, mithilfe dieser können Parameter die eingesetzt werden typisiert werden. Zudem wird nicht mehr einfach der ganze String ausgefürt, sondern die Parameter auch weiterhin nur als Parameter behandelt. Eine Ausfürung des SQL Statements welches injected wurde, findet auf keinen Fall mehr statt. Trotzdem sollte jeder Parameter sauber überprüft werden, nicht das evlt. JavaScript in die DB geschrieben wird, welcher den User dann bei Aufruf der Homepage angreift.
