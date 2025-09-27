2025-09-27 17:10

Tags: [[machine learning]]

------------------------------------------------

##### Overview:
In order to perform a logistic regression, we need a different cost function to calculate our mean error.
Final function: 
$$J(x,y)=-\frac{1}{n}\sum_{i=1}^n[y^{(i)}log(f(x^{(i)}))+(1-y^{(i)})log(1-f(x^{(i)}))]$$

##### Why not MSE?
We can not use the mean square error function for this reason:
As you can see below, if we insert our logistic function for f(x) in the MSE function, the resulting graph is not convex. This means there are lots of local minima, which would cause gradient descent to go into the first of those minima and never reach the global minima.
![[2025-09-27-171335_hyprshot.png]]
*HINT: Moving the $\frac{1}{2}$ into the summation does not change the math but makes this easier to explain down the road*

##### The new function:
First of all, we split the formula for the summation from the rest and call it the loss function. This is nothing else than the error function for one single point. The cost function now looks like this:
$$J(w,b)=\frac{1}{n}\sum_{i=1}^{n}L(f(x^{(i)}), y^{(i)})$$
For the new loss function, we will utilize the negative log function. Plotted, it looks like this: 
![[2025-09-27-172304_hyprshot.png]]
With 0 being an asymptote, meaning f(0) = $\infty$

Since the output of our function is always between 0 and 1, the only relevant part lies where the x-value is also in that interval.
As you can see, if the value is 1 and the predicted value is also 1, the loss is 0. If the value is 1 and the predicted value is 0, the loss is infinitely big as it is the biggest distance from the correct point. If our value is 0 however, we need to push $1 - f(x)$ into the log function to get this graph:
![[2025-09-27-173006_hyprshot.png]]
This gives us the horizontally inverted graph, resulting in the correct loss in case our value is 0.

We can sum these two cases up using some clever math:
$$L(f(x^{(i)}), y^{(i)})=-y^{(i)}log(f(x^{(i)}))-(1-y^{(i)})log(1-f(x^{(i)}))$$
Which results in the correct formula for both cases.

Now we just insert it into the cost function and move the negative prefixes outside the summation to get this final formula:
$$J(x,y)=-\frac{1}{n}\sum_{i=1}^n[y^{(i)}log(f(x^{(i)}))+(1-y^{(i)})log(1-f(x^{(i)}))]$$
##### Implementing in code:
For this loss function, we will not be able to use a vectorized form, meaning we have to loop over each example and calculate the mean in the end.
In this example, X is a vector of all input variables with the shape (amount of examples, number of features), y is a vector of the correct results for all examples with the shape(amount of examples, 1), w is a vector of all coefficients with the shape (number of features, 1) and b is the y-intercept (Achsenabschnitt). 

Code:

`def compute_logistic_cost(X,y,w,b):`
	`m = X.shape[0]`
	`cost = 0.0`
	`for i in range(m):`
		`z = np.dot(X[i], w) + b`
		`f_transformed = 1 / (1 + np.exp(-z))`
		`cost = cost + ((-y[i] * np.log(f_transformed )) - (1-y[i] * np.log(f_transformed)))`
	`cost = cost / m`
	`return cost`






------------------------------------------------------
### References
https://github.com/greyhatguy007/Machine-Learning-Specialization-Coursera/blob/main/C1%20-%20Supervised%20Machine%20Learning%20-%20Regression%20and%20Classification/week3/Optional%20Labs/C1_W3_Lab05_Cost_Function_Soln.ipynb
https://www.youtube.com/watch?v=YkTcK_LXAxw&list=PLkDaE6sCZn6FNC6YRfRQc_FbeQrF8BwGI&index=35