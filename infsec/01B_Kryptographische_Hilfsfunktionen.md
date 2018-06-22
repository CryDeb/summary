# Kryptographische Hilfsfunktionen
## Warum Hashfunktionen gebraucht werden
* Überprüfen ob zwei riesige Datein gleich sind.
* Um Identifikationsmerkmale, welche nicht im Klartext gespeichert werden sollen (auf DB) zu persistieren.

## Kryptographisch gute Hashfunktionen besitzten:

**Preimage Resistance**
Es ist praktisch nicht möglich aus einem gehaschten wert ein Urbild zu finden. Man spricht von der Urbildresistenz oder der Einweg-Eigenschaft.


**Strong Collision Resistance**
Es ist praktisch nicht möglich zwei verschiedene Urbilder mit dem gleichem Bild y (Hash) zu finden. Man nennt diese Eigenschaft auch starke Kollisionsresistenz.


**2nd-preimage Resistance**
Es ist praktisch nicht möglich eine Zweites x zu finden, welches gehashed dasselbe y ergiebt wie das erste x. Mann spricht dann von der Resistenz gegen zweites Urbild oder von schwachen Kollisionsresistenz.


## Realisiertung
Realisierung von Hashfunktionen — Padding Eine Hashfunktion nimmt eine beliebige lange Meldung und produziert daraus einen Hash fixer Länge. In der Praxis wird die Meldung in gleich lange Blöcke unterteilt.

### Padding / Auffüllen des Letzten Blockes
Nach dem letzten Bit der Meldung wird eine 1 eingefügt und danach so viele Nullen, dass am Ende des vollen Blockes die 64-Bit Darstellung der Länge der Meldung vor dem Padding Platz hat.


### Versionen
Grundsätzlich 2 Versionen:

* Dedizierte Hashfunktion (explizit zum Hashen)
* Auf Blockchiffren basierend (z.B. einfach AES verwendet sollte vermieden werden, da langsam und kleine blöcke)


### Blockchiffre Basierende
#### Davies-Meyer
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-Davies-Meyer.png}
    \caption{Die Davies-Meyer Kompressionsfunktion}
\end{figure}

#### Matyas-Meyer-Oseas
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-Matyas-Meyer-Oseas.png}
    \caption{Matyas-Meyer-Oseas}
\end{figure}

#### Merkle-Damgard
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-Merkle-Damgard.png}
    \caption{Merkle-Damgard Konstruktion}
\end{figure}


### SHA-1

### SHA-3


## Message Authentication Codes (MAC)

* ist eine kryptographische Authentifizierungsmarke für eine bestimmte Meldung
* basiert auf einem geheimen, nur dem Sender und Empfänger bekannten symmetrischen Schlüssel
* generiert aus einer beliebig (endlich) grossen Meldung ein Authentifizierungsmarke fixer Länge.
* stellt die Authentizität des Absenders, sowie die Integrität der empfangenen Meldung sicher
* Die Realisierung erfolgt mittels kryptographischer Hashfunktionen


\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-MAC-Integrity.png}
    \caption{Merkle-Damgard Konstruktion}
\end{figure}

### Keyed-Hash Message Authentication Code (HMAC)
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-HMAC.png}
    \caption{HMAC}
\end{figure}


## Zufallsgenerator
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-Zufallsgenerator.png}
    \caption{HMAC}
\end{figure}

### Arten von Zufallsgeneratoren

* echte Zufallsgenerator -> Echte Zufallszahlen kann man aus chaotischen physikalischen Prozessen erhalten
  * Radioaktiver Zerfall
  * Wurf einer fairen Münze oder eines fairen Würfels
  * Rauschen in elektronischen Bauteilen
  * Schwankungen der Drehzahl in Harddisks
  * Bilder von Lavalampen
  * Verkehrslärm
  * Netzwerkverkehr
* Pseudo Zufallszahlengeneratoren -> Erzeugen aus einer Zufallszahl (Seed) einen Strom von Pseudozufallszahlen
