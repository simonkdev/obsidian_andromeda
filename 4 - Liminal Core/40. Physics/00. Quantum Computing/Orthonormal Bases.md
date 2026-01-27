2026-01-26 17:21

Tags:  [[Physics]] [[vectors]] [[mathematics]] [[quantum computing]] [[Spin]]

------------------------------------------------
### Definition:
An **orthonormal** base for [two]-dimensional kets consists of [two] **unit** kets which are **orthogonal** to one another. This means that for two kets $a$ and $b$ to form an orthonormal basis, the equations $\braket{a|a} = 1$, $\braket{b|b} = 1$ and $\braket{a|b})= 0$ have to be true. One example of this is the pair
$$\displaylines{
\ket{a} = \begin{bmatrix} 0 \\ 1\end{bmatrix} \newline
\ket{b} = \begin{bmatrix} 1 \\ 0 \end{bmatrix}
}$$

### Directions:
We will use three important orthonormal bases, all with special interpretations regarding spin.
$$ \displaylines{
\ket{\uparrow} = \begin{bmatrix} 1 \\ 0 \end{bmatrix} ,
\ket{\downarrow} = \begin{bmatrix} 0 \\ 1\end{bmatrix} \newline
\ket{\rightarrow} = \begin{bmatrix} \frac{1}{\sqrt{2}} \\\frac{-1}{\sqrt{2}} \end{bmatrix} ,
\ket{\leftarrow} = \begin{bmatrix} \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} \end{bmatrix} \newline
\ket{\nearrow} = \begin{bmatrix} \frac{1}{2} \\ \frac{-\sqrt{3}}{2}\end{bmatrix} , \ket{\swarrow} = \begin{bmatrix} \frac{\sqrt{3}}{2} \\ \frac{1}{2}\end{bmatrix} \newline
}$$
### Notation:
An orthonormal base is noted like this:
$$
\{ \ket{b_1}, \ket{b_2}, \ket{b_3}, \ket{b_4}, \ket{b_5}, \space ..\space , \ket{b_n} \}
$$
With n being the targeted dimension of the basis.

### Ordered Bases:
while the order of their elements does not matter  for normal bases, it does matter for ordered ones. To denote this, we simply exchange the curly brackets for parentheses:
$$ \displaylines {
\{ \ket{b}, \ket{a}\} = 
\{ \ket{a}, \ket{b}\}
\newline
(\ket{a}, \ket{b}) \ne 
(\ket{b}, \ket{a})
}$$
These become useful when we differ between measuring the [[spin]] of an electron with the South-magnet on top or bottom.





------------------------------------------------------
### References
Quantum Computing for Everyone - Chris Bernhardt, MIT Press