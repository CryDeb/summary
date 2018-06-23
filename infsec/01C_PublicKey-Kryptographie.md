# Public Private Key Kriptographie

## RSA Ver/Entschlüsselung
\begin{figure}[H]
    \centering
    \includegraphics[width=1\textwidth]{images/01C-RSA_Schluesselerzeugung.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=1\textwidth]{images/01C-RSA_Verschluesselung.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=1\textwidth]{images/01C-RSA_Entschluesselung.png}
\end{figure}

## RSA Signieren
\begin{figure}[H]
    \centering
    \includegraphics[width=1\textwidth]{images/01C-RSA_Signatur.png}
\end{figure}

## RSA Angriffen
\begin{figure}[H]
    \centering
    \includegraphics[width=1\textwidth]{images/01C-RSA_Angriffe.png}
\end{figure}


## Homomophe Verschlüsselungen
Homomorphe VerschlüsselungenMit Hilfe homomorpher Kryptographie lassen sich Operationen (wie Addition, Multiplikation,Concatenation, etc.) auf dem Geheimtext durchführen, die mathematischen Operationen desentsprechenden Klartextes entsprechen.

## Diffie-Hellman zu Elgamal
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth, angle=90 ]{images/01C-Diffie1.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth, angle=90]{images/01C-Diffie2.png}
\end{figure}

## Elgamal
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth, angle=90]{images/01C-Elgama.png}
\end{figure}

## Diskrete Logarithmus
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01C-DiskreteLog.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01C-DikreteLog2.png}
\end{figure}

### Wir haben Public-Key Verfahren kennengelernt als ein Kryptosystem wo jeder Benutzerein Schlüsselpaar verwendet: einen privaten (geheimen) und einen öffentlichen Schlüssel.

RSA ist das erste wirklich brauchbare Public-Key Verschlüsselungssystem. Schulbuch RSA ist aber verletzlich für verschiedene Angriffe. Deshalb wurde OAEP entwickelt

Diffi-Hellman kann erweitert werden zum Public-Key Verschlüsselungssystem Elgamal.

Die Homomorphieeigenschaft eines Verschlüsselungssystems erlaubt Berechnungen auf dem Klartext auf dem Ciphertext durchzuführen. Das entschlüsselte Resultat derBerechnung auf dem Ciphertext ist dann gerade das Resultat des Klartextes. Damit istsicheres Cloudcomputing möglich.

Das Problem des diskreten Logarithmus ist verantwortlich dafür, dass Diffi-Hellman undElgamal sicher sind. Das Faktorisierungsproblem ist verantwortlich für die Sicherheit von RSA.

Die Elliptic Curve Cryptography (ECC) erlaubt effientere Berechnungen weil kürzereSchlüssel und einfachere Operationen. Sowohl RSA, wie auch Diffie-Hellman und Elgamallassen sich mit ECC implementieren.
