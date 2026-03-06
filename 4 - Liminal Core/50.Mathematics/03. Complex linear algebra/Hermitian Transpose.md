2026-03-06 09:08

Tags:  [[complex linear algebra]] [[linear algebra]] [[matrices]] [[vectors]]

------------------------------------------------

### General:
Also called the complex transpose or "dagger" ($\dagger$) operation, the Hermitian transpose is a combination of the regular transpose and the complex conjugation applied to all entries. 
$$
A^{\dagger} = \overline{(A^T)}
$$
For example, applied to a $\mathbb{C}^{3x3}$ matrix, it looks like this:
$$
A = 
\begin{bmatrix} 
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33} \\
\end{bmatrix},
\space \space \space 
A^{\dagger} = 
\begin{bmatrix}
\overline{a_{11}} & \overline{a_{21}} & \overline{a_{31}} \\
\overline{a_{12}} & \overline{a_{22}} & \overline{a_{32}} \\
\overline{a_{13}} & \overline{a_{23}} & \overline{a_{33}}
\end{bmatrix}
$$
It applies to vectors as well, since vectors are just a special case of matrices.






------------------------------------------------------
### References
https://minireference.com/linear_algebra/linear_algebra_with_complex_numbers