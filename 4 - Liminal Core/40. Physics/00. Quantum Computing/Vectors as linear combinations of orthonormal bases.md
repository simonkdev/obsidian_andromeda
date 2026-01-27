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

### Length of vectors that are written as linear combinations:
Just a handy formula for calculating the vector length of these linear combinations:
$$ \displaylines {
\ket{v} = \braket{ b_1 | v}\ket{b_1} + \braket{ b_2 | v}\ket{b_2} + \braket{ b_4 | v}\ket{b_3}+ \space .. \space  +\braket{ b_n | v}\ket{b_n}
\newline
\text{define: } \braket{b_i | v} = c_i
\newline
\ket{v} = c_1 \ket{b_1} + c_2 \ket{b_2} + c_3 \ket{b_3} + \space .. \space + c_n \ket{b_n}
\newline
\bra{v} = c_1 \bra{b_1} + c_2 \bra{b_2} + c_3 \bra{b_3} + \space .. \space + c_n \bra{b_n}
\newline
\rightrightarrows 
\braket{v|v} = (c_1 \ket{b_1} + c_2 \ket{b_2} + c_3 \ket{b_3} + \space .. \space + c_n \ket{b_n})(c_1 \bra{b_1} + c_2 \bra{b_2} + c_3 \bra{b_3} + \space .. \space + c_n \bra{b_n})
\newline
\text{Since } \braket{b_i | b_k} = 0 \text{ if } i \ne k \text{ and } = 1 \text{ if } i = k:
\newline
\braket{v|v} = c_1² + c_2² + c_3² + \space .. \space + c_n²

}$$







------------------------------------------------------
### References
Quantum Computing for Everyone - Chris Bernhardt, MIT Press