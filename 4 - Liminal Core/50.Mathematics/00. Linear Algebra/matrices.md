2025-09-08 19:11

Tags: [[mathematics]]

------------------------------------------------

##### 0. Overview:
A matrix is essentially what a 2-dimensional array represents in programming. Its size is determined by multiplying the amount of rows by the amount of columns. Each element consists of a letter (in this case, a / the lowercase of the name) and the number of the row followed by the number of the column:
$$ A = \begin{pmatrix} a11 & a12 & a13 \\ a21 & a22 & a23 \\ a31 & a32 & a33 \end{pmatrix}
$$
(size = $3 * 3 = 9$)

##### 1. Adding / Subtracting:
You can add / subtract matrices of the same dimensions (above: `3x3`) by adding or subtracting the numbers in the same positions. For example, if an identical matrix as A was to be added to A, we would add $a12$ to $b12$ and $a31$ to $b31$ etc.

##### 2. Scalar Multiplication:
Each element is multiplied by the factor, matrix stays the same size. Example:

$$ \begin{pmatrix} 2 & 3 & 4 \\ 4 & 8 & 1 \end{pmatrix} *  4 = \begin{pmatrix} 8 & 12 & 16 \\ 16 & 32 & 4 \end{pmatrix}  $$

##### 3. Representing a linear system with matrices:
a linear system with three equations like this: 
$$ 
4x - y + 2x = 7
$$
$$
x + 3 + 5z = 16
$$
$$
2x + 3y -4z = 9
$$
would look like this represented with matrices:

```
General Form: Ax = b; each of the variables being a matrix; A = coefficients, x = variables, b = results
```
$$ \begin{bmatrix} 4 & -1 & 2 \\ 1 & 3 &5 \\ 2&3&-4 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} = \begin{bmatrix} 7 \\ 16 \\ 9 \end{bmatrix} $$
###### 3.1 Elementary Row Operations:
In order to perform any of these, we need to create an augmented matrix, which is just taking the b matrix from above and placing it on the right of the A matrix from above. Often, you will see a line separating them like this:
$$ \begin{bmatrix} 4 & -1 &2 &|&7 \\ 1 & 3 & 5 &|&16\\ 2 & 3 & -4&|&9 \end{bmatrix}$$
Performing any of these operations will not change the solution, thus possibly making them easier to find.
###### 3.1.1 Interchanging:
You just swap two rows with each other.

###### 3.1.2 Scaling:
You multiply each value of one row with a factor (like vector scaling for one row).

###### 3.1.3 Replacement by addition:
You can choose to replace a row with the sum of the row itself and one or more other rows. Rows not included in the sum may not be replaced by it.


------------------------------------------------------
### References
https://www.youtube.com/watch?v=ZFVFtVbeerI