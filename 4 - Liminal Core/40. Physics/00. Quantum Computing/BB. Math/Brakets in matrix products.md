2026-01-27 11:19

Tags:  [[Physics]] [[vectors]] [[mathematics]] [[quantum computing]] [[Spin]] [[matrices]]

------------------------------------------------

### General:
Any matrix can be written as a vector containing vectors, for example:
$$ \displaylines{
A = \begin{bmatrix} 2 & 3 & 4\\ 5 & 6 & 7 \end{bmatrix} = \begin{bmatrix} 
\bra{a_1} \\ \bra{a_2}
\end{bmatrix}
\newline \text{ where: }
\newline \bra{a_1} = \begin{bmatrix} 2 & 3 & 4 \end{bmatrix}
\newline \text{ and: }
\newline \bra{a_2} = \begin{bmatrix} 5 & 6 & 7 \end{bmatrix}
}$$
This is useful for dot products, as the result just becomes a matrix of braket operations:
$$\displaylines{
A = 
\begin{bmatrix} 
\bra{a_1} 
\\ 
\bra{a_2} 
\\ 
\bra{a_3} 
\\ 
.. 
\\ 
\bra{a_m} 
\end{bmatrix},
B = 
\begin{bmatrix} 
\ket{b_1} & \ket{b_2} & \ket{b_3} & .. & \ket{b_n} 
\end{bmatrix}
\newline
AB = 
\begin{bmatrix} 
\braket{a_1|b_1} & \braket{a_1|b_2} & \braket{a_1|b_3} & .. & \braket{a_1|b_n} 
\\
\braket{a_2|b_1} & \braket{a_2|b_2} & \braket{a_2|b_3} & .. & \braket{a_2|b_n} 
\\
\braket{a_3|b_1} & \braket{a_3|b_2} & \braket{a_3|b_3} & .. & \braket{a_3|b_n}
\\ 
.. & .. & .. & .. & ..
\\
\braket{a_m|b_1} & \braket{a_m|b_2} & \braket{a_m|b_3} & .. & \braket{a_m|b_n} 
\end{bmatrix}
}$$
Note that the bras and kets need to have the same dimensions for the braket operation, which is why the dot product only works for two matrices of sizes (m, r) and (r, n).




------------------------------------------------------
### References
Quantum Computing for Everyone - Chris Bernhardt, MIT Press
