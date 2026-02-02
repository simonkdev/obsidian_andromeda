2026-01-24 16:00

Tags: [[Physics]] [[vectors]] [[mathematics]] [[quantum computing]]

------------------------------------------------

### General:
Kets and Bras are just vectors, except it is the Dirac notation, which brings some special operations with it. It is not used broadly outside of quantum computing, but there it is the standard. 

### General notation:
Kets are just vertical vectors, but they are written as  $\Ket{a} = \begin{bmatrix} 2 \\ 3 \\ 4 \\ 69 \end{bmatrix}$ 
Bras are horizontal vectors, written as $\bra{a} = \begin{bmatrix} 2 & 3 & 4 & 69 \end{bmatrix}$

### Dimensions:
Dimension is just the amount of entries a vector contains. For $\bra{a}$ and $\ket{a}$ from above: 4


### Bra-kets:
If we want to multiply a bra by a ket (or the other way around) of the same dimension, we denote it as a braket $\braket{a | b}$.

For example, with $\bra{a} = \begin{bmatrix} 2 & 3 & 4 & 5 & 6 \end{bmatrix}$ and $\ket{b} = \begin{bmatrix} 9 \\ 8 \\ 42 \\ 3 \\ 12 \end{bmatrix}$ , we write:
$$\braket{a | b} = \bra{a} * \ket{a}=  \begin{bmatrix} 2 & 3 & 4 & 5 & 6 \end{bmatrix} \begin{bmatrix} 9 \\ 8 \\ 42 \\ 3 \\ 12 \end{bmatrix} = 2*9 + 3*8 + 42*4 + 5*3 + 6*12 = 297$$
(it is just a dot product like in [[matrices]], except with the Dirac notation)

### Length of a vector:
Since we can display a vector¹ as an arrow, we can determine the length of that arrow using the Pythagorean Theorem. The length of bras and kets is denoted as $|\bra{a}|$ and $|\ket{a}|$ respectively. 
The arrow would be the hypothenuse, so we can say: $$|\ket{a}| = \sqrt{\ket{a}[0]² + \ket{a}[1]²}$$
In the case of our example above, it would look like this:
$$|\ket{a}| = \sqrt{2² + 3² + 4² + 69²} = \sqrt{4790} \approx 69,2$$


### Orthogonal vectors:
Deriving from the pythagorean theorem, we can say that if the squared sum of two [[vectors]] is equal to the sum of their squares, these three form a right triangle. Therefore, the two initial vectors must be perpendicular or, as it is phrased in quantum theory, orthogonal. 
In Dirac notation, this is the required equation:
$$|\ket{a}|² + \ket{b}|² = |\ket{a+b}|²$$

### Brakets and Lengths:
If we have two identical vectors, with one being denoted as the ket $$\ket{a} = \begin{bmatrix} a_1 \\ a_2 \\ .. \\ a_n \end{bmatrix}$$ and the other as the bra $$\bra{a} = \begin{bmatrix} a_1 & a_2 & .. & a_n \end{bmatrix}$$
We can see that the braket is:
$$\braket{a|a} = a_1² + a_2² + .. + a_n²$$
Which means that the length of a can be written as:
$$|\ket{a}| = \sqrt{\braket{a|a}}$$
Because:
$$|\ket{a}| = \sqrt{a_1² + a_2² + .. + a_n²} = \sqrt{\braket{a|a}}$$
Now since a [unit vector] is just a vector with length 1 and the root of 1 is also 1, we can establish that if $\braket{a|a} = 1$, the vector is a unit vector.

### Brakets and Orthogonality:
Proving that two vectors $a$ and $b$ are orthogonal if $\braket{a|b} = 0$ is best described in a mathematical equation. We recall that two vectors are orthogonal if $|\bra{a} + \bra{b}|² = |\bra{a}|² + |\bra{b}²|$.

let
$$\bra{a} = \begin{bmatrix} a_1 & a_2 & a_3 \end{bmatrix} \ \ and \ \ \bra{b} = \begin{bmatrix} b_1 & b_2 & b_3 \end{bmatrix} $$ 
then
$$ \displaylines{|\bra{b} + \ket{a}|² = \begin{bmatrix} a_1+b_1 & a_2+b_2 & a_3+b_3 \end{bmatrix}\begin{bmatrix} a_1+b_1 \\ a_2+b_2 \\ a_4+b_3 \end{bmatrix}
= (a_1+b_1)² + (a_2+b_2)² + (a_3+b_3)² \newline = a_1² + 2a_1b_1 + b_1² +  a_2² + 2a_2b_2 + b_2² +  a_3² + 2a_3b_3 + b_3² \newline = a_1² + a_2² + a_3² + b_1² + b_2² + b_3² + 2(a_1 b_1 + a_2b_2 + a_3b_3)
\newline = |\bra{b}|² + |\ket{a}|² + 2 \braket{a|b}}$$
As you can see, the equation $|\bra{a} + \bra{b}|² = |\bra{a}|² + |\bra{b}²|$ is only true if $\braket{a|b} = 0$. Therefore, two vectors are orthogonal if their braket-product is 0.


 







¹ only two- or three-dimensional ones

------------------------------------------------------
### References
Quantum Computing for Everyone - Chris Bernhardt, MIT Press