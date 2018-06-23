# Kryptographische Protokolle
## Protokolle

* Alle Beteiligten kennen jeden Schritt des Protokolls bereits im Voraus und sie erklärensich bereit diesen Schritten exakt zu folgen.
* Das Protokoll muss eindeutig, unmissverständlich und vollständig sein, d.h. es darfbeispielsweise keine Zweifelsfälle geben, in denen sich die Parteien nicht deterministischverhalten könn(t)en.
* Das Protokoll gibt keine Informationen preis, die nicht durch das Protokoll spezifiziertsind. Ein Protokoll kann also nicht ausgenützt werden um an Informationen zu gelangen,die nicht bereits das Protokoll offen legt.

### Unterscheidung
* Vermittelte Protokolle
  * bei denen ein Vermittler mitbeteiligt ist (bei Kerberos ist es beispeilsweise das key distribution center (KDC); beim Erwerb von Wohneigentum ist es beispielsweise der Notar). Dies führt natürlich zu grösseren Kosten, mehr Zeit und allenfalls zu einem Flaschenhals!
* Adjudicated Protocolls
  * ziehen allenfalls einen Schiedsrichter als dritte Partei bei, welche beispielsweise bei Unklarheiten den weiteren Verlauf des Protokolls festlegt. Der Schiedsrichter greift aber nur dann ein wenn sich zwei oder mehr Parteien nicht einigen können (Beispiele sind Spiele im Sport wie Fussball).
* Self Enforcing Protocols
  * setzen Fairness durch, ohne dass Dritte dafür sorgen: Mogelt eine Partei, dann bemerkt dies die andere und stoppt das Protokoll. Diese Art von Protokollen ist anzustreben, da sie wenig Overhead und Kosten verursacht und auch keine externe Hilfe benötigt.


### Grundbausteine
* Kommunikation mittels symmetrischer Kryptographie
* Kommunikation mittels public-key Kryptographie, sowie hybride Systeme (mit Sitzungsschlüssel).
* Einweg-Funktionen, um beispielsweise Hash-Werte zu erzeugen oder um Einwegfunktionen mit Hilfe einer Falltür umkehrbar zu machen (Falltür Einweg-Funktion).
* Einweg Hash-Funktionen,und MAC’s.
* Digitale Signaturen, die entweder symmetrische Kryptographie und einen Notar(Arbitrator), public-key Kryptographie, Zeitstempel (engl: timestamps)und Einweg-Hashfunktionen verwenden, und nicht abstreitbar sein sollen.
* Digitale Signaturen + Verschlüsselung mit Empfangsbestätigungen (gegen resend attacks).
* Zufallsgeneratoren

## Authentifizierung -> KDF
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-KDF1.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-KDF2.png}
\end{figure}

## Challenge-Response-Protocol
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-CRP1.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-CRP1.png}
\end{figure}

## Perfect Forward Secrecy (PFS)
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-PFS1.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-PFS2.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-PFS3.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-PFS4.png}
\end{figure}
TODO

## Kereberos
TODO

## Schlüsselaustausch mit symetrischen Schlüssel
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-SAMAV1.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-SAMAV2.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-SAMAV3.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-SAMAV4.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-SAMAV5.png}
\end{figure}

## Zero-Knowledge-Protokolle
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-ZKP1.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-ZKP2.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-ZKP3.png}
\end{figure}
TODO

## Commitment (Verbindliche Festlegung)
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-COM1.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-COM2.png}
\end{figure}
TODO

## Blinde Signaturen
TODO

## Geteilte Geheimnisse
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-GETEILT1.png}
\end{figure}
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{images/01D-GETEILT2.png}
\end{figure}
TODO
