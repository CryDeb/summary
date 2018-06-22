# Secret- / Privatekey Cryptography (Symmetrische Verschlüsselung)
## Was ist Kryptographie
Kriptograpihe fasst 2 Teilgebiete zusammen:
* ** Kryptographie: ** beschäftigt sich mit der Entwicklung von Algorithmen
* ** Kryptoanalyse: ** untersucht die Sicherheit von Verschlüsselungsalgorithmen.

### Secret- / Privatekey Cryptography (Symmetrische Verschlüsselung)
Die Secret-/Privatekey Cryptography befasst sich mit von Alters her gewohnten Methode des Ver- und Entschlüsselns mit einem einzigen, jedem Kommunikationspartner bekannten Schlüssel

### Kreckhhoff-Prinzip
Der Angreifer kennt den Algorithmus zum Ver- bzw. Entschlüsseln der Daten immer: es darf lediglich angenommen werden, dass der von den Teilnehmern verwendete Schlüssel geheim ist.

## Geschichte
### Skytala
Papyrusstreifen auf dem die Nachricht geschrieben wird rollt man um ein Rundholz und schreibt die Nachricht in Richtung Rotationsachse. Die nachricht ist nun durch den Durchmesser des Rundholz verschlüsselt. Allfällige gegenparteien benötigen ein Rundholz welches den selben Radius aufweist.

### Cäsar-Chiffre
Die Cäsar-Chiffre ist ein einfaches symetrisches Verschlüsselungsverfahren. Bei der Verschlüsselung wird jeder Buchstabe des Klartexts (m) auf einen Geheimbuchstabet(c). Diese Abbildung ergibt sich, wenn der Buchstabe (m) um eine bestimmmte Anzahl(k) zyklisch nach rechts verschoben wird. Es resultiert die folgende leichung:

c = (m + k) mod 26

### Vigenère-Chiffre
Einfach gesagt wird eine Matrix erstellt, welche in der Ersten Zeile ein kompletes alphabet enthält, sowie in der ersten Spalte. Die Spalte definiert, von wo das Alphabet weitergefüht wird, ist man zu ende und noch nicht am ende der Zeile angelangt so beginnnt man das alphabet von vorne. Mit diese Matrix (gefüllt mit Buchstaben kann nun ein Klartext mittels einem Schlüsselwort/satz entschlüsselt werden. Dazu nimmt man den Buchstaben des Klartextes mit dem stellenpandant zum Geheimtext, falls dieser zu kurz ist wird er ohne leerzeichen wiederholt. Nun sucht man in der Ersten Zeile nach dem gewünschten Spalte, nämlich dijenige, welche den Buchstaben des Klartextes enthält und in der ersten Spalte um die gewünschte Zeile zu erhalten, wieder die Zeile, welche den Buchstaben enthält diesmal jedoch die des Schlüsseltextes. Wo sich nun die Spalte mit der Zeile kreuzt steht der Buchstabe, welcher als Verschlüsselung genutzt werden soll.

### Vernam-Chiffre
Wie die Vigenère-Chiffre aber mit einem Schlüsselwort, welches gleich lang ist wie die Nachricht.
Sofern das Schlüsselwort aus zufälligen Buchstaben, dann bietet diese Methode perfekte Sichreheit.

### Rote Telefon


### Rotormaschinen

## Feistelnetzwerk -> Feistelchiffre
\begin{figure}[H]
    \centering
    \includegraphics[width=0.3\textwidth]{images/01A-Feistelchiffre.jpg}
    \caption{Eine Runde einer Feistelchiffre}
\end{figure}
Das Feistelnetzwerk / chiffre ist ein ferfahren gemäs der beiliegenden grafik. Als erstes wird ein Input (Block) in zwei Teile geteilt. Der Rechte teil des Blockes wird nun mit dem Schlüssel in eine Funktion f1 hineingegeben. Diese liefert einen gleichlangen Block zurück. Diese Rückgabe wird schliesslich mit dem Linken Teil mittels XOR verknüpft. Nun erhält man einen völlig Random aussehenden Block, sofern der Key Random ist. Diese XOR verknüpfung liefert uns wieder einen neuen Block, welches neu der neue Rechte Block wird. Der neue Linke Block wird der alte Rechte Block. Dieser Ablauf ist genau eine Runde. Da eine Runde noch nicht sicher ist, da der Linke Teil so nicht Zufällig aussieht, sondern die Unverschlüsselte message noch enthält, muss dieser Ablauf mindestens 2mal durchlaufen werden, damit der ganze Output block nach einer Zufallsfolge aussieht.

## Substitutions-Permutationsnetzwerke (SPN)
\begin{figure}[H]
    \centering
    \includegraphics[width=0.7\textwidth]{images/01A-Substitutions_Permutationsnetzwerke.jpg}
    \caption{Eine Runde eines Substitutions-Permutationsnetzwerkes und deren Ende}
\end{figure}
Bei einem Substitutions-Permutationsnetzwerk wird ein Inputblock mit dem Schlüssel über ein XOR gatter zu einem neuen Block transferiert. Anschliessend wird der Block in weitere Subblöcke aufgesplittet. Diese aufgesplitteten subblöcke werden anschliessend in eine Substitutionsbox (S-Box) hineingeführ. In dieser werden die Input werte gemäs einer, für jeweiles genau diese box, definierte Tabele in einen ausgangsblock umgewandelt. Anschliessend werden alle ausgänge der S-Boxen wieder zusammengeführt, um schliesslich in einer Permutationsbox (P-Box) zu landen, wo die Inputstellen in einer definierten folge neue Positionen einnehmen. Die Ausgabe der P-Box ist schliesslich das Ende der Runde. Dies könnte beliebieb häuffig wiederholt werden. Bei der Letzten Runde kann jedoch auf die P-Box verzichtet werden, zumal diese öffentlich zugänglich ist. Zudem sollte vorher noch einmal ein XOR mit dem Schlüssel gemacht werden.

## Data Encryption Standard (DES)
\begin{figure}[H]
    \centering
    \includegraphics[width=0.5\textwidth]{images/01A-DES_Function_and_key.jpg}
    \caption{Eine Runde der F Funktion von DES}
\end{figure}
Der Data Encryption Standard (DES) ist ein weit verbreiteter symmetrischer Verschlüsselungsalgorithmus.
Er ist eine simple Feisterchiffre mit einem Substitutions-Permutationsnetzwerk als Funktion F (funktion F siehe Abbildung).

### Schlüssel
Schwache Schlüssel führen zu weniger als 16 unterschiedlichen Rundenschlüssel, d.h. einige, oder gar alle Rundenschlüssel sind indentisch. Beispielsweise:

* Alles Nullen oder Einsen
* Die eine Hälfte Nullen, die andere Einsen und vice versa
* Abwechslungsweise Nullen und Einsen, etc.


### Double / Tripple DES
Damit Triple DES rückwertskompatible zu DES bleibt, wurde für Triple DES folgende Verschlüsselung gewählt (E für Encrypt DES, D für Decrypt DES):
Cyphertext = E(D(E(Plaintext, Key1), Key2), Key1)

Diese Formel würde bei Key1 = Key2 folgendes ergeben:
Cyphertext = E(D(E(Plaintext, Key1), Key2), Key1) = E(P, Key1)

Es würde nichts bringen einen 3ten Schlüssel zu gebrauchen, da dieser durch Meet-In-The-Middle schnell entschlüsselt werden könnte.

#### Sicherheit Meet-In-The-Middle Angriff double DES

Gehen wir mal davon aus, dass wir einen Klartext (P) und den Passenden Geheimtext (C) kennen. Double DES würde ja wie folgt funktionieren:
E(E(Plaintext, Key1), Key2)
Hätten wir nun Eben Plaintext und Cyphertext so könnte man den Key von beiden Seiten herrechnen und folgende formel würde sich ergeben:
E(Plaintext, Key1) = D(Cyphertext, Key2)

Wir können also beide Schlüssel schnell ausfindig machen mit Folgender Methode:

1. Wir erstellen eine Tabelle, welche den Plaintext mit allen möglichen Schlüsseln ausrechnet. Wir krigen also 2^56 Halbcyphertexte.
2. Wir erstellen eine zweite Tabelle, welche den Cyphertext mit allen möglichen Schlüsseln Entschlüsselt. Wir kriegen also wieder 2^56 Halbcyphertexte.
3. Wir vergleichen die Halbcyphertexte von Schritt 1 und 2 und überprüfen all jene die den gleichen Halbcyphertext ergeben, falls es mehrere Treffer gibt, so überprüft man den match mit einem zweiten Plaintext/Cyphertext pärchen.

Es stellt sich nun also heraus das der aufwand lediglich 2*2^56 beträgt. Es ist also nur Notwendig 2^57 mal den schlüssel zu berechnen und wir haben schon beide schlüssel errechnen können. Es sind also nicht die erhoften 2^112 .

## Advanced Encryption Standard (AES)
Es wurde einen ersatzt für DES gesucht, welcher dank der gestiegenen Rechenleistung nach kurzerzeit mit Brutforce geknackt werden konnte.
Nach einer Ausschreibung von 1997 haben sich 15 AES Kandidaten beworben, von welche es noch 5 in die Endrunde schaften.
Die 5 Kandidaten waren

Naem | Komplexität | Geschwindigkeit | Sicherheit
---- | ----------- | --------------- | ----------
Mars | komplex | schnell | hoch
Serpent | einfach-sauber | langsam | hoch
Rijndael(gewinner) | einfach-sauber | schnell | genutzt
RC6 | sehr einfach | sehr schnell | niedrig
Twofish | komplex | schnell | hoch

### AES verfahren
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/01A-AES_ablauf.jpg}
    \caption{Eine Runde von AES}
\end{figure}
Jede Runde von AES besteht aus drei Schichten.
1. Nicht-lineare Substitutionsschicht (S-Boxen)
2. Lineare Mixing-Layers (Schiften der Rows)
3. Key Addition Layer (XOR mit Rundensclüssel)


## Betreibsmodi von Block-Chiffren
Da wir beim verschlüsseln der Daten immer nur einzelne Blöcke von X Bites verschlüsseln können, muss ein verfahren her, damit eine Nachricht, welche Länger als die X Bites, so verschlüsselt wird, dass am schluss alle Blöcke verschlüsselt sind.

### Electronic Code Book
\begin{figure}[H]
    \centering
    \includegraphics[width=0.5\textwidth]{images/01A-ECB.png}
    \caption{Eine Runde der F Funktion von DES}
\end{figure}
Ein sehr einfaches verfahren. Die Plaintext nachricht wird in XBites blöcke unterteilt. Ist der Letzte zu klein wird dieser mit Nullen aufgefüllt.
Die Blöcke werden am schluss nur aneinandergekettet und so übertragen.
Risiger nachteil entsteht dadurch, dass fals es in der Nachricht übereinstimmungen im Plaintext gibt, diese auch im Cyphertext übereinstimmend sind. Dies ist nicht gut für die Sicherheit.

#### Sicherheit


* Muster im Klartext werden nicht versteckt (-).
* Klartext kanneinfachmanipuliertwerden, d.h. Blöcke können einfach dazu geügt, entfernt, vertauscht oder wiederholt werden (-).
* Input für die Block-Chiffre ist nicht randomisiert sondern gleich dem Klartext (-).
* Man kann mehr als eine Meldung mit demselben Schlüssel verschlüsseln (+).

#### Effizienz


* Die selbe Geschwindigkeit wie die Block-Chiffre (+).
* Infolge Padding wird der Chiffretext maximal um einen Block länger als der Klartext (-).
* Es ist nicht möglich, gewisse Berechnungen im Voraus zu machen (-).
* Allerdings kann die Berechnung parallelisiert werden (+).

### Cipher Block Chaining
\begin{figure}[H]
    \centering
    \includegraphics[width=0.5\textwidth]{images/01A-CBC.png}
    \caption{Eine Runde der F Funktion von DES}
\end{figure}
Beim Cipher Block chaining wird vor dem Verschlüsseln der Klartext mit dem vorangegangenen Verschlüsselten String ge XOR't. Beim ersten Block kommt der IV (Inizialisierungsvektor) dazu.

#### Sicherheit


* Muster im Klartext werden versteckt, da dieser mit dem vorhergehenden Geheimtext XOR-verknüpft wird (+).
* Durch diese Operation wird der Input für die Block-Chiffre auch randomisiert (+).
* Wie beim ECB kann mehr als eine Meldungmit dem selben Schlüssel verschlüsselt werden (+).
* Manipulation des Klartextes ist ziemlich schwierig (+/-)

#### Effizienz


* Die selbe Geschwindigkeit wie die Block-Chiffre (+).
* InfolgePaddingwirdderChiffretext maximal um einen Block länger als der Klartext (-).
* Es ist nichtmöglich, gewisse Berechnungen im Voraus zu machen (-).
* Verschlüsselung ist nichtparallelisierbar (-);
* Entschlüsselung ist aber parallelisierbar und hat zudem dierandom-accessEigenschaft.


### Cipher FeedBack
\begin{figure}[H]
    \centering
    \includegraphics[width=0.5\textwidth]{images/01A-CFB.png}
    \caption{Eine Runde der F Funktion von DES}
\end{figure}
Beim Cipher FeedBack wird beim erstenmal der IV (Inizialisierungsvektor) Verschlüsselt anschliessend diser mit dem Klartext ge XOR't.
Der nun verschlüsselte Block wird wieder Verschlüsselt um anschliessend wieder mit dem nächsten klartext block ge XOR't zu werden.

#### Sicherheit


* Muster im Klartext werden versteckt (+)
* und auch der Input für die Block-Chiffre wird randomisiert (+).
* Wird jedes Mal ein neuer IV verwendet,können auchmehrere Meldungen mit dem selben Schlüssel verschlüsselt werden (+).
* Manipulation des Klartextes ist ziemlich schwierig (+/-).

#### Effizienz


* Die selbe Geschwindigkeit wie die Block-Chiffre (+).
* ChiffratistsolangewiederKlartext - ohne IV (+).
* Verschlüsselung ist nicht parallelisierbar (-);
* Entschlüsselung ist aber parallelisierbar und hat zudem dierandom-access Eigenschaft. Der vorige Block kann bereits verschlüsselt werden, bevor der Klartextbekannt ist - danach muss nur noch die XOR-Operation durchgeführt werden (+).


### Output FeedBack
\begin{figure}[H]
    \centering
    \includegraphics[width=0.5\textwidth]{images/01A-OFB.png}
    \caption{Eine Runde der F Funktion von DES}
\end{figure}
Beim Output Feedback fürd der IV (Inizialisierungsvektor) verschlüsselt und dieser Verschlüsselte Block mit dem Klartext ge XOR't. Der Verschlüsselte IV wird vor jedem XOR nochmals verschlüsselt.



#### Sicherheit


* Muster im Klartext werden versteckt (+)
* und auch der Input für die Block-Chiffrewird randomisiert (+).
* Wird jedes Mal ein neuer IV verwendet,können auchmehrere Meldungen mit dem selben Schlüssel verschlüsselt werden (+).
* Klartext kann einfach verändert werden, da jede Änderung des Chiffretexts den Klartext direkt beeinflusst (-).


#### Effizienz


* Die selbe Geschwindigkeit wie die Block-Chiffre(+).
* Chiffratistsolange wie der Klartext - ohne IV (+).
* Berechnungen können bereits gemachtwerden, bevor der Klartext bekannt ist (+).
* OFB ist nicht parallelisierbar (-)
* Countermode dagegen schon (+)!


### Counter Mode
\begin{figure}[H]
    \centering
    \includegraphics[width=0.5\textwidth]{images/01A-CM.png}
    \caption{Eine Runde der F Funktion von DES}
\end{figure}
Beim Counter mode wird der IV (Inizialisierungsvektor) Verschlüsselt und dieser wird dan mit dem Klartext ge XOR't beim zweiten/i ten block wird der IV mit i ge XOR't Verschlüsselt und anschliessend mit dem klartext ge XOR't.



## Stromchiffren
\begin{figure}[H]
    \centering
    \includegraphics[width=0.5\textwidth]{images/01A-Stromchiffren.jpg}
    \caption{Eine Runde der F Funktion von DES}
\end{figure}
Einfach siehe bild!


## RC4
TODO??
