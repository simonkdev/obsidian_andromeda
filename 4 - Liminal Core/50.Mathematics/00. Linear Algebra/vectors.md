2025-08-20 17:45

Tags: [[linear algebra]]

------------------------------------------------
##### General:
a vector is essentially an array with multiple components. what it represents is different depending on the context. For example, a displacement vector (in physics) is represented by one component per dimension, each with the difference between the start and end value. 
Furthermore, a displacement vector that moves a point in 4-dimensional space 1 unit in x, 2 units in y, 5 units in z and 15 units in the time dimension would look like this: 
`v = [1, 2, 5, 15]`
If you want to represent a point with coordinates relative to the origin (0,0,0), the displacement values equal the position values
making the coordinates and the **positional vector** the same: 
`a(23,14,76)` represents the same as `p = [23,14,76]`.

##### Notation:
In math and physics, a vector will normally contain components that are real numbers (R) or integers (Z).

A vector can be represented as the group its components stem from raised to the power equal to the amount of components it contains. For example, the position vector already shown above could be described as $Z³$. Sometimes (although less precise) vectors can also be described as 3-vectors (in this case, number changes ofc.)

Normally (in math / physics), a vector is expressed like this:
$a = (2, 4)$

In computer science, a vector is usually expressed like an array consisting of the vector's components:
`a = [2, 4]`

*Other notations*:

An x-array can be expressed as a one-dimensional array: `v[x]`

It can also be expressed as a dict, each dimension being expressed through a key:

`a = {0:2, 1:4}`


##### Arithmetic operations on vectors:

- *Vector addition:*
	To add two vectors together, add the value from each component to the corresponding value of the other vector. This returns the corresponding value of the new vector. Since the start and end locations of a vector don't matter (only the difference between them), any two vectors can be added (no need for the second one to start at the first one's end position). 
	Logically, only vectors with the same amount of components can be added:
	$$ a = (14,12) ; b = (8,-6) ; a + b = (22, 6)$$

- *Vector scaling:*
	To scale a vector, simply multiply each component by the scalar to receive the new one:
	$$ a = (5, 8); m = 2; a*m = (10,16)$$

- *Convex combination:*
	used in computer games, the expression looks like this:
	$$ (a * u) + (b * u)$$
	where $u$ and $v$ are vectors and $a$ and $b$ are each positive decimal numbers that add to 1 ($a + b = 1$).
	If $u$ and $v$ are plotted from the same point of origin, the expression returns a new vector that, if plotted from the same point of origin, would end up on a line connecting the tips of $u$ and $v$:
	![[2025-08-20-183429_hyprshot.png]]
- *Dot product*:
	an operation that returns a scalar value (). The general expression looks like this:
	$$u * v = (u1​ x v1​) + (u2​ x v2​) + (un​ x vn​).$$
	meaning to multiply a vector by another vector, you must multiply each component with the corresponding component from the different vector (similar to vector addition) and then add those products together. Logically, only vectors with the same amount of components can be multiplied with each other. For example:
	$$ a = (1,3,5); b = (12,-4,7) ; a * b = (1 * 12) + (3 * -4) + (5 * 7) = 12 + -12 + 35 = 35 $$
	


------------------------------------------------------
### References
https://adacomputerscience.org/concepts/struct_vector