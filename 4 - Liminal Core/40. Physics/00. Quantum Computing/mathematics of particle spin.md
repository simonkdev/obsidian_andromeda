2026-01-28 14:36

Tags: [[Physics]] [[Spin]] [[Orthonormal Bases]] [[Vectors as linear combinations of orthonormal bases]] [[quantum computing]] [[mathematics]] [[calculating ordered orthonormal basis for measurements]]

------------------------------------------------

Choosing a direction to measure spin is equivalent to choosing an ordered [[Orthonormal Bases]] (basis).
The vectors in the basis correspond to the *possible outcomes* of the measurement.

Before measuring, the particle will be in a spin state represented by the state vector (or state for short).  This state vector is always written as a *linear combination* of the chosen basis, with this form for state vector $\ket{s}$:
$$
\ket{s} = c_1\ket{b_1} + c_2\ket{b_2}
$$
Here, $c_1$ and $c_2$ are called *probability amplitudes*. Their squares represent the *probability* of the measured state being $\ket{b_1}$ or $\ket{b_2 }$  respectively. After measuring, the state vector always jumps to being the measured state. 


### Example:
Simulating a two-measurement experiment where first, we measure spin in the vertical direction, then measure spin in the horizontal direction.

1. We don't know the state of the particle, but we do know it is a unit vector. Therefore, we can write it as $\ket{s} =  c_1\ket{\uparrow} + c_2\ket{\downarrow}$  with $c_1² + c_2² = 1$.
2. After measuring, the particle is deflected upwards, meaning $\ket{s} = \ket{\uparrow}$.
3. We switch to a different ordered orthonormal basis, this time corresponding to the vertical direction (since this is what we want to measure). We know the state vector, meaning we can determine the probability of either result. We will be using this equation:
$$ \displaylines{
\ket{s} = \ket{\uparrow} = c_1\ket{\rightarrow} + c_2\ket{\leftarrow}
\newline
\longrightarrow \begin{bmatrix} c_1 \\ c_2 \end{bmatrix} = \begin{bmatrix} \ket{\rightarrow} & \ket{\leftarrow} \end{bmatrix}^T\ket{s}
}$$
(see [[matrices for orthonormal basis verification]], last section)
4. Calculating the above term, we get the results $\frac{1}{\sqrt{2}}$ for both $c_1$ and $c_2$.
5. This means that the probability of either spin N or S in the horizontal direction is $(\frac{1}{\sqrt{2}})²$, or *0.5* for short.

### Very simple words:
1. State is always combination of basis vectors.
2. If we know the state before measuring and the measurement direction, we can determine the probability of the result by determining the *probability amplitudes* $c_1$ and $c_2$. 
3. After each measurement, the state changes to the one measured.




------------------------------------------------------
### References
Quantum Computing for Everyone - Chris Bernhardt, MIT Press