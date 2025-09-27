2025-09-09 21:15

Tags: [[machine learning]]

------------------------------------------------
##### Overview:
Beim gradient descent geht es darum, den Gesamtfehler ( Fehler = Differenz) zu minimieren, um sich der tatsächlichen Funktion anzunähern. 
Hierfür verwendet man gradients und Updates. 
*HINT: The final algorithm is all the way on the last point called "Batch Gradient Descent Algorithmus"*

##### Step-by-Step:
1. Parameter initialisieren:
	Startwerte für m und b, z.B. 0, festlegen
	"Lernrate"  $\eta$ festlegen, z.B. 0,1
2. Fehler / Differenz / Abweichung für alle Punkte berechnen mit der Formel für den Gesamtfehler
3. Gradienten berechnen ( siehe unten für Formeln)
4. Parameter neu belegen mit Update-Funktion (siehe unten)
5. Wiederholen ab Schritt 2
Mit jeder Wiederholung wird die Funktion präziser.
*HINT: Ganz unten findet sich der tatsächliche Algorithmus, der zum Programmieren verwendet wird und diese Schritte durch Zusammenfassen der einzelnen Formeln kombiniert.*

##### Gesamtfehler:
Die allgemeine Formel für den Gesamtfehler bzw. die Gesamtdifferenz lautet wie folgt:

$$J = \frac{1}{n} \sum_{i=0}^n((m * x_i + b) -y_i)² $$
Dabei gilt:
- J = Gesamtfehler
- n = Anzahl der Datenpunkte
- i = index des aktuellen Datenpunktes
- m,b = geschätzte Koeffizienten
- $y_i$ = tatsächlicher aktueller Output Value
- $x_1$ = aktueller Input Value
Der Gesamtfehler repräsentiert den Durchschnitt der quadrierten Differenzen.

##### Gradients:
Die zwei Formeln für die beiden Gradienten lauten wie folgt:
Für m:
$$\frac{\delta J} {\delta m} = \frac{2}{n} \sum_{i=1}^nx_ie_i$$
Für b:
$$\frac{\delta J}{\delta b} = \frac{2}{n}\sum_{i=1}^ne_i$$
Mit der eingesetzten Gesamtfehler - Formel sehen sie aus wie folgt:
Für b:
$$\frac{\delta J}{\delta b} = \frac{2}{n}\sum_{i=1}^n((m * x_i + b) -y_i)$$
(Für m entsprechend mit x am ende multipliziert)
*HINT: manchmal sieht man auch die Gesamtfehler-Formel mit $\frac{1}{2n}$ und die Gradients mit $\frac{1}{n}$, was rechnerisch identisch ist. Wichtig ist, keinen der Brüche doppelt zu verwenden.*
##### Update-Formel:
Die Update-Formel lautet wie folgt:
Für m:
$$m_{neu} = m_{alt} - \eta * \frac{\delta J}{\delta m}$$
Für b:
$$b_{neu} = b_{alt} - \eta * \frac{\delta J}{\delta b}$$


##### Je..desto für $\eta$ :
Je kleiner, desto langsamer und stabiler der Prozess.
Je größer, desto schneller und wahrscheinlicher zum Überschuss der Prozess.


##### Batch gradient descent Algorithmus:
Der finale Algorithmus kombiniert die Gradient- und Update-Formeln mit den unten erläuterten Erweiterungen:
$$\theta_j := \theta_j - \alpha \frac{1}{n}\sum_{i=0}^n(h_\theta(x^{(i)}) - y^{(i)})x_j^{(i)}$$
*Erweiterungen:*

$\theta$ = Vektor aller Parameter, sieht hier so aus: $\begin{bmatrix} \theta_1 \\ \theta_2 \\ \theta_3 \\ . \\ . \\ . \\ \theta_j \end{bmatrix}$ (j = Anzahl)

$x^{(i)}$ = Vektor aller Features / Inputs, sieht genauso aus, wobei in diesem fall $x^{(i)}_{1 bzw. 0} = 1$ und $x^{(i)}_{2 bzw. 1} = x^{(i)}$, um sicherzustellen, dass nur bei m mit x multipliziert wird. Dementsprechend ist $x^{(i)}$ einfach nur der Wert x (Input) für den i-ten Datenpunkt

*HINT: Im Algorithmus, den wir im Code verwenden, muss x eine Matrix aller features sein, weshalb es da so aussieht: $\begin{bmatrix} 1 & x^{(1)} \\ 1 & x^{(2)} \\ 1 & x^{(3)} \\ . \\ . \\ . \\ 1 & x^{(n)} \end{bmatrix}$ . Das ist einfach der Unterschied zwischen Theorie und Praxis. Außerdem wird der Vektor hier als X (groß X) und der Input als $x^{(i)}$ bezeichnet*

$\alpha = \eta$ 

$h_\theta(x) = \theta^Tx = \theta_0 + \theta_1x_1$, wobei $\theta^Tx$ eine Vektor-Multiplikation darstellt, bei der $\theta^T$ die transponierte Version von $\theta$ darstellt ($\theta$ als Zeilenvektor) und $x$ den Feature-Vektor. der letzte Teil entspricht demnach $m * x + t$. $h_\theta$ ist ein Vektor mit allen Prognosen für y. $\theta_0 + \theta_1x_1$ ist die allgemeine Formel für alle vorhergesagten werte (ohne die weighing-reihe von x), diese ist allerdings bei $\theta^Tx$ enthalten, da $\theta$ der Vektor aller Koeffizienten und $x$ der Vektor aller Inputs bzw. Features ist. Gebildet wird das dot product (siehe [[matrices]], Abschnitt 4). 


:= --> "ersetze durch", Zuweisung-Zeichen in der Mathematik

Fully vectorised for reference: 
$$\theta := \theta - \alpha \cdot \frac{1}{n} X^T \left( X\theta - y \right)$$


------------------------------------------------------
### References
https://chatgpt.com/c/68c07a60-c834-8320-b832-36eac6b25f65

