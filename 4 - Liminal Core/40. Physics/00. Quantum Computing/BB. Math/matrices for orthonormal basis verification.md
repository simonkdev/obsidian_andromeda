2026-01-27 11:40

Tags:  [[Physics]] [[vectors]] [[mathematics]] [[quantum computing]] [[Spin]]

------------------------------------------------

### General:
We can use a matrix to check wether a set of [[Kets and Bras]] forms an orthonormal basis.
We recall that, in order for this, the vectors need to be unitary and ortogonal, represented by these equations:
$$\displaylines{
\braket{b_i|b_k} = 0
\newline
\braket{b_i| b_i} = 1

} $$
Furthermore, an identity matrix' entries (i, i) are $1$ and (i, k) or (k, i) respectively $0$.
	(see section 5 in [[matrices]])
By arranging the set we want to verify in a matrix and checking wether $A^TA = I_n$, we can see if the set is an orthonormal basis. We also only need to compute half the brakets outside the diagonal because the result of the brakets $\braket{b_i| b_k}$ and $\braket{b_k|b_i}$ are identical.

### Representing a vector as a linear combination of an orthonormal basis as a matrix:
We know that $$\ket{v} = \sum_{i=1}^{n}\braket{b_i|v}\ket{b_i}$$
And we can express it like this:
$$A^T\ket{v} = \begin{bmatrix} \bra{b_1} \\ \bra{b_2} \\ \bra{b_3} \\ .. \\ \bra{b_n} \end{bmatrix} \ket{v} = \begin{bmatrix} \braket{b_1 | v} \\ \braket{b_2 | v} \\ \braket{b_3 | v} \\ .. \\ \braket{b_n | v} \end{bmatrix} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ .. \\ x_n \end{bmatrix}$$






------------------------------------------------------
### References
Quantum Computing for Everyone - Chris Bernhardt, MIT Press