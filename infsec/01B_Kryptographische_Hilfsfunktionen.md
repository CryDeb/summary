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

### Linear Kongruente Zufallsgenerator
Eine einfache formel, welche eine Statistische gute Zufallszahl generiert. Diese ist jedoch für die Kryptographie nicht brauchbar, da sie durch lösen des folgenden gleichungssystemes geknackt werden kann:
  s1 = (as1 + b) mod m
  s2 = (as2 + b) mod m

s ist der seed (sozusagen die stelle welche ich möchte -> also 3 bedeutet, der wert wenn ich das 3te mal berechne)
a b und m sind parameter.


### Linear Feedback Shift Register (LFSR)
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-LFSR.png}
    \caption{Ablauf eines LFSR}
\end{figure}
Ein LFSR ist ein lineares Shiftregister mit Rückkopplung, wobei aus einigen Registerwerten durch XOR-Verknüpfung ein neuer Registerwert berechnet wird. Dieser neue Wert wird links ins Registergeschoben und im gleichen Zug werden alle Registereinträge um eine Stelle nach rechts geschoben. Ausgegeben wird das ganz rechts herausfallende Bit.

#### Nachteil
Da es für ein LFSR der Länge L nur 2L mögliche Zustände gibt, muss sich die Belegung des LFSR nach einer bestimmten Zeit wiederholen. Der Output eines LFSR ist also periodisch. die maximale Periode eines LFSR beträgt 2^L - 1.

##### Sicherheit
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-LFSR_A5.png}
    \caption{Ablauf eines LFSR bei GSM}
\end{figure}


* Falls 2L Output Bits eines LFSR der LängeLbekannt sind, lassen sich die Feedback Koefizienten c1 bis cl durch lösen eines Systems von linearen Gleichungen berechnen.
* Aus diesem Grunde werden Kombinationen von LFSR verwendet. (siehe bild)


\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-LFSR_A5.png}
    \caption{Ablauf eines LFSR bei GSM}
\end{figure}

### Nicht lineare Feedback Shift Register (Trivium)
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01B-Trivium.png}
    \caption{Trivium}
\end{figure}

Im der neuen Stromchiffre Trivium werden 3 Shift Register A, B und C mit Längen 93, 84 und 111 verwendet.

* **Initialisierung:** Ein 80-Bit IV wird in den linken Teil von A geladen und ein 80-Bit Schlüssel in den linken Teil von B. Alle anderen Register werden Null gesetzt mit Ausnahme dass C109=C110=C111=1 gesetzt wird.
* **Aufwärmphase:** der Cipher wird 4 x 288 = 1152 Mal geclockt ohne den Output zu verwenden.
* **Ver-/Entschlüsselungsphase:** Ab dem 1153. Clock wird der Output verwendet um mit dem Klartextbit XOR-verknüpft zu werden.
* Trivium kann extrem kompakt in Hardware implementiert werden.
* deswegen ist Trivium schon mit minimalster Hardware sehr schnell
* Bis jetzt sind keine Angriffe bekannt, was nicht heisst, dass dieser relativ neue Cipher auch wirklich sicher ist.


### Testen ob Bitfolge zufällig ist

* **Monobit Test** Seien n0 und n1 die Anzahl Nullen und Einsen im Bitstring. Dann ist die Zufalsvariable \begin{equation*} x = \frac{(n_0 - n_1)^2}{n} \end{equation*}   wichtig n sollte >= 10 sein. Aussage es sollten schliesslich 50% sein.

* **Two-Bit Test** Seien n00, n01, n10 und n11 die Anzahl Vorkommen von 00, 01, 10 und 11 im Bitstring. Dann ist die Zufallsvariable \begin{equation*}x = \frac{4}{n-1} * (n_{00}^2+n_{01}^2+n_{10}^2+n_{11}^2)-(2/n) * (n_0^2+n_1^2)+1 \end{equation*}

* **Maurers universal statistical test:** Idee: Eine Zufallsbitfolge lässt sich nicht komprimieren!


## Einwegfunktionen
Wenn ein Glas in tausend Stücke zerspringt weiss jeder, dass man diesen Vorgang nicht rückgängig machen kann. Es handelt sich also um eine Einwegfunktion (die Zerstörung ist einfach, das Rückgängigmachen geht nicht). Obwohl in der Kryptographie einige Funktionen eingesetzt werden, von denen man vermutet, dass es sich um Einweg-Funktionen handelt, ist der mathematische Beweis zu deren Existenz bisher noch nicht gelungen.

Einige mögliche Einweg-Funktionen mit Falltür sind:
 * Modulares Quadrieren
 * Modulare Exponentation
 * Die RSA Funktion
 * Die Rabin Funktion

### Modulares Quadrieren

\begin{figure}[H]
    \centering
    \includegraphics[width=1\textwidth]{images/01B-Modulares-quadrieren.png}
\end{figure}

### Exponentation/RSA/Rabin


\begin{figure}[H]
    \centering
    \includegraphics[width=1\textwidth]{images/01B-Einwegfunktion-overview.png}
\end{figure}
