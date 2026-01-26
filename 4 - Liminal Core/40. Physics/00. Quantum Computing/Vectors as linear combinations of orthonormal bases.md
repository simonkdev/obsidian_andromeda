2026-01-26 17:44

Tags: [[Physics]] [[vectors]] [[mathematics]] [[quantum computing]]

------------------------------------------------

### General:
Given a ket and an orthonormal basis, we can express the ket as a linear combination of the basis vectors. 

### Proof:
$$ \displaylines{
\begin{bmatrix} c \\ d \end{bmatrix} = x_1 \ket{\rightarrow} + x_2 \ket{\leftarrow} \space \space \space \space \space \space | *\bra{\rightarrow}
\newline
\bra{\rightarrow}\begin{bmatrix} c \\ d \end{bmatrix}= x_1\braket{\rightarrow | \rightarrow} + x_2\braket{\rightarrow | \leftarrow}
\newline
\bra{\rightarrow}\begin{bmatrix} c \\ d \end{bmatrix}= x_1 * 1 + x_2 * 0
\newline
\text{(brakets of the same arrows are one and of different zero because they are unit and orthogonal)}
\newline
x_1 = \bra{\rightarrow}\begin{bmatrix} c \\ d \end{bmatrix}
\newline ...
\newline
x_1 = (c-d) / \sqrt{2}
\newline ...
\newline
\begin{bmatrix} c \\ d \end{bmatrix}= \frac{(c-d)}{\sqrt{2}}\ket{\rightarrow} + \frac{(c+d)}{\sqrt{2}}\ket{\leftarrow}
}$$

### Abstraction:
Now, we can show that any vector of any dimension can be represented by an orthogonal basis for that dimension. 
$$ \displaylines{
\ket{v} = x_1\ket{b_1} + x_2\ket{b_2} + x_3\ket{b_3} ... x_i\ket{b_i}
\newline
\text{again, the braket of }b_i\text{ and } b_k \text{ where } i = k \text{ is 1, otherwise zero, therefore:}
\newline
x_i = \braket{b_i | v}

}$$




------------------------------------------------------
### References
Quantum Computing for Everyone - Chris Bernhardt, MIT Press