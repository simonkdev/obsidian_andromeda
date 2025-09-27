2025-09-27 15:26

Tags: [[machine learning]]

------------------------------------------------

##### Overview:
Logistic regression is a classification algorithm. It uses binary classification, meaning the output is either Present (1) or Absent (0)
The logistic regression function is just a linear regression whose output is being passed through the sigmoid function (or logistic function). 
This function always outputs a value between 0 and 1, which is to be taken as the probability that the logistic value is 1.
One more thing is different: for logistic regression, we use the [[logistic loss function]] instead of the normal MSE one.

##### The sigmoid function:
The sigmoid function uses the constant $e$ (Eulers constant) in a fraction to produce this graph:
![[2025-09-27-153207_hyprshot.png]]
$$g(x) = \frac{1}{1+e^{-x}}$$
The resulting value is always between 0 and 1, with 0 being equal to $\frac{1}{1-e⁰} = \frac{1}{1+1} = \frac{1}{2} = 0.5$

##### Implementation:
We simply use gradient descent with a linear regression but put our predictions through the sigmoid function before calculating the difference.
In python, the function looks like this:

`def sigmoid(z):`
    `g = 1/(1+np.exp(-z))`
    `return g`

##### Polynomial decision boundaries:
If we now combine polynomial and logistic regression, we can get very complex shapes like an ellipse or even more complex ones, resulting 
in a model that is incredibly powerful and accurate.
![[2025-09-27-155044_hyprshot.png]]

##### Vectorised form of logistic gradient descent:
Performing a logistic gradient descent consists of two steps that are different from linear:
1. calculate z (prediction for y)
2. pass z through sigmoid function

- 1) Calculating Z (vector of all z):
	math:	$$w^TX+B$$
	(B being a `1xm` matrix with all values b)
	code:
				`Z = np.dot(w.T, X) + b`
- 2) pass Z through sigmoid function
	math: $$\frac{1}{1+e^{-Z}}$$
	code:
				`A = 1 / (1 + np.exp(-Z))`

From here, you can use the vectorized form of gradient descent just like we did with polynomial and linear regression.






------------------------------------------------------
### References
https://www.youtube.com/watch?v=xuTiAW0OR40&list=PLkDaE6sCZn6FNC6YRfRQc_FbeQrF8BwGI&index=32
https://www.youtube.com/watch?v=0az8RjxLLPQ&list=PLkDaE6sCZn6FNC6YRfRQc_FbeQrF8BwGI&index=33