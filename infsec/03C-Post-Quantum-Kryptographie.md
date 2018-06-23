## Post Quantum Kryptographie
### Unterscheiden Sie perfekte und rechnerische Sicherheit. Geben Sie je ein Beispiel.
**Perfekte Sicherheit**
* Ein Krypto-Verfahren ist perfekt sicher, wenn es auch von einem Angreifer mit unbeschraenkten Ressourcen nicht gebrochen werden kann, d.h.
  * Unbeschraenkte Speicherkapazitaet und Rechenzeit
  * Keine Technologie bedingten Einschraenkungen (z.B. Quantencomputer)
  * Keine rechnerischen / mathematischen Annahmen (z.B. Faktorisieren ist schwer)
* Synonyme fuer perfekte Sicherheit sind absolute Sicherheit, uneingeschraenkte Sicherheit oder informationstheoretische Sicherheit
* Das Gegenteil von perfekter Sicherheit ist rechnerische Sicherheit
* Claude Shannon hat 1949 bewiesen, dass der One-Time-Pad von Vernam aus dem Jahre 1918 perfekt sicher ist
**Rechnerische Sicherheit**
* Ein Krypto-Verfahren ist rechnerisch sicher, wenn jeder bekannte Algorithmus mindestens exponentielle Laufzeit oder exponentiellen Speicherbedarf in Bezug auf die Schluessellaenge aufweist.
* Beispiel:
  * Brute-Force Suche bei AES-128 hat eine Zeitkomplexitaet von O(2 ( 128))
  * Meines Wissens hat das aktuell beste, allgemeine Verfahren eine Zeitkomplexitaet von O(2 ( 126.1)) - also rund 4x schneller
  * AES gilt also als rechnerisch (sehr) sicher, aber nicht perfekt sicher
  * Aber es gibt keine Garantie, dass nicht doch ein effizienter Angriff existiert

### Welchen praktischen Einschränkungen unterliegt der One-Time-Pad?

### Brechen Sie einen One-Time-Pad, wenn zweimal der gleiche Schlüssel verwendet wurde.
Der Angreifer geht dabei von folgender Ueberlegung aus: Angenommen, der Absender hat für beide verschluesselten Nachrichten (versehentlich) denselben Schluessel verwendet, dann kann der Angreifer die Differenz der beiden verschluesselten Texte analysieren. Klartexte und folglich auch Differenzen von Klartexten zeigen naemlich im Gegensatz zu Zufallstexten eine Reihe von Auffaelligkeiten, die statistisch ausgewertet und zur Entzifferung ausgenutzt werden können. So zeigt die Buchstabenhaeufigkeit von Differenztexten ebenso charakteristische Auffälligkeiten wie bspw. die von Klartexten oder von monoalphabetisch verschluesselten Texten.

### Beschreiben Sie Ihr Vorgehen bei der Wahl der Schlüssellänge in einer kryptographischen Implementation.
1. Sicherheitsbeduerfniss abklaeren.
2. Abklaeren wie lange die Daten geschuetzt sein sollen.
3. Auswahl eines geeignetes kryptographischen Verfahrens (symetrisch, asymetrisch ...)
4. Auswahl der boentigten Schluessellaenge. Die Angabe, wie lange Daten geschuetzt sein sollen ist hier Massgeben.
Um Punkt 3 und 4 zu klaeren wuerde ich mit Empfehlungen der Sicherheitsdienste arbeiten. Das Bundesamt fuer Sicherheit in der Informationstechnik (Deutschland) stellt zum Beispiel ein Dokument BSI - Technische Richtlinie Kryptographische Verfahren: Empfehlungen und Schluessellaengen zur Verfuegung

### Was würde die Existenz eines Quantencomputer für RSA bedeuten?
Bereits 1994 praesentierte Peter Shor von AT T Bell Labs einen Algorithmus zum Faktorisieren von Zahlen auf einem Quantencomputer Dieser hat nahezu quadratische Zeitkomplexitaet. Sobald also Quantencomputer gebaut werden koennen, muessen wir RSA zu Grabe tragen.

### Was würde die Existenz eines Quantencomputer für ElGamal & ECC bedeuten?
Der Algorhitmus von Peter Shor zum Faktorisieren von Zahlen auf einem Quantencomputer berechnet den diskreten Logarithmus in Polynomialzeit. Also duerften auch ElGamal und Co. nicht mehr verwendet werden.

### Was würde die Existenz eines Quantencomputer für AES bedeuten?
Symmetrische Krypto scheint Quantum-resistent.

### Was versteht man unter dem Begriff Post-Quantum Kryptographie?
Post-Quantum Kryptographie bezeichnet die Suche nach kryptographischen Verfahren, die auch einem Quantencomputer Stand halten wuerden. Einige Erfolgsmeldungen gibt es bereits:
* Niemand bricht den One-Time-Pad!
* Symmetrische Krypto scheint Quantum-resistent. Der aktuell beste Algorithmus von Grover halbiert (nur) die Schluessellaenge von z.B. AES
* Asymmetrische Verfahren basierend auf mathematischen Gittern (vgl. Seerosen) sind nach aktuellem Wissen Quantum-resistent. Zudem basieren sie im Gegensatz zu RSA, ElGamal und ECC auf mathematischen Problemen, die als NP vollstaendig bewiesen worden sind.
* Andere asymmetrische Verfahren werden aufgrund der Marktdominanz von RSA kaum eingesetzt.

### Welches praktische Problem löst die Quantenkryptographie?
Zum Beispiel das Austauschen eines Schluessels fuer die Symetrische Verschluesslung kann durch einen Quantenkanal sicher ausgetauscht werden. Quantenschluesselaustausch Für den Quantenschluesselaustausch wird kein Quantencomputer, aber quantenmechanische Kohaerenz der übertragenen Signale benoetigt. Die dazu noetigen technischen Voraussetzungen existieren bereits; ein Beispiel: Im April 2004 wurde vom Rathaus in Wien zu einer in der Stadt ansaessigen Bank ein mit Quantenkryptographie verschluesselter Geldtransfer ausgeloest. Bei den gegenwaertigen Glasfasertechnologien ist allerdings die Entfernung zwischen Sender und Empfänger beschraenkt, da wegen der erforderlichen Kohaerenz die ueblichen Signalverstaerker nicht einsetzbar sind. Die hoechste (Stand: 2008) per Glasfaserkabel ueberbrueckte Entfernung, bei der ein Quantenschluessel ausgetauscht wurde, betraegt 184,6 km, durchgefuehrt im Jahr 2006.

###  Wie wird mittels BB84 ein Schlüssel ausgetauscht?
TODO

###  Wie wird der mittels BB84 ausgetauschte Schlüssel verwendet.
TODO
