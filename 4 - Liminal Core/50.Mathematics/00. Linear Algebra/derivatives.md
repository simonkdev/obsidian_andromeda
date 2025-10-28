2025-10-28 16:13

Tags: [[gradient descent]] [[mathematics]] [[matrices]]

------------------------------------------------

##### General:
Eine Ableitung / derivative zeigt die Steigung an einem bestimmten Punkt einer Funktion an.
Dies macht sie, indem sie durch den Punkt eine Tangente zieht.
In der Theorie funktioniert das über das Zusammenziehen von zwei Punkten, durch die eine Gerade
gezogen wurde. In der Realität verwendet man Ableitungsregeln, um die Ableitungen vom Funktionsterm
abzulesen.

##### Theorie:
Zwei beliebige Punkte auf dem Graphen, auf dem die Steigung ermittelt werden soll. 
Der Punkt, für den die Steigung bestimmt werden soll ist der linkere Punkt. 
Durch beide wird eine Linie gezogen und wir bilden eine Sekante.
Es gilt: die Steigung der Sekante wird errechnet durch: $\frac{\delta y}{\delta x}$, also den Abstand auf der y-Achse
geteilt durch den Abstand auf der x-Achse. Errechnen wir den Limes dieser Funktion (für $\delta x$ -> 0 konvergiert der Graph),
erhalten wir die Steigung.

Einen allgemeinen Ableitungsterm für einen Funktionsterm erhalten wir über das Einsetzen des Terms in diese Formel:

$$
f'(x) = \lim_{\delta x \to 0} \frac{f(x + \delta x) - f(x)}{\delta x}
$$
Anschließend wird gekürzt. Hier am Beispiel von $x²$:

$$
\quad f(x) = x^2
f'(x) = \lim_{\Delta x \to 0} \frac{(x + \Delta x)^2 - x^2}{\Delta x}
= \lim_{\Delta x \to 0} \frac{2x\Delta x + (\Delta x)^2}{\Delta x}
= \lim_{\Delta x \to 0} (2x + \Delta x)
\Rightarrow \boxed{f'(x) = 2x}

$$


##### Gradient descent-Bezug:

![[Drawing 2025-10-28 16.38.35.excalidraw]]



------------------------------------------------------
### References
https://chatgpt.com/c/6900ea07-2248-832c-a81f-6c0bf3aa1904
https://www.youtube.com/watch?v=uZ_KsEaryZI
https://studyflix.de/mathematik/ableiten-4212
https://www.youtube.com/watch?v=N2PpRnFqnqY