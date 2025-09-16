2025-09-12 21:06

Tags: [[machine learning]] 

------------------------------------------------

##### Overview:
Here you will find a step-by-step description of an univariable linear regression (UVLR) in python.

##### Code:
`import numpy as np`
`import pandas as pd`
`import matplotlib.pyplot as plt`
`import seaborn as sns`
`%matplotlib inline`

`df = pd.read_csv('data/ex1data1.txt')`
`df.columns = ['population', 'profit']`
--> Loading the needed data into a pandas dataframe

`ax = sns.scatterplot(data=df, x='population', y='profit')`   
`ax.set(xlabel='Population of City in 10,000s', ylabel='Profit in $10,000s', title='Scatter plot of training data')`


`n = df.shape[0]`
n = number of data pairs

`X = np.hstack((np.ones((n, 1)),
`df.population.values.reshape(n, 1)))`
--> making a feature array with one column consisting of just ones so that theta is balanced (m needs to be multiplied by x in the algorithm, b does not. the theta array consisting of m and b will later be multiplied by this array, which is where the effect comes into play (see delta in function gradient_descent))


`Y = df.profit.values.reshape(n,1)`
--> an array of the actual solutions used for comparison later on

`iterations = 1500`
`alpha = 0.01`

`def compute_cost(X, Y, theta):`
    `n = X.shape[0]           # the shape of X and shape of theta: n x 2 and 2 x 1 --> h must have shape n x 1` 
    `h = X.dot(theta)`
    `J = ((1/2*n) * np.sum((h-Y) **2))`
    `return J`
--> optional helper function, this just calculates the average error our function has so we can see if and how our model improved.

`def gradient_descent(X, Y):`
    `n = X.shape[0]`
    `theta = np.zeros((2,1))`
    
    `for i in range(0, iterations):`
        `h = X.dot(theta)`
        `diff_hy = h - Y` 
        `delta = diff_hy.T.dot(X)`
        `theta = theta - (alpha * (1/n) * delta.T)`
    
    `return theta`
--> key algorithm. The most important part is happening in delta and theta, where the batch algorithm from [[gradient descent]] is used in the form of code.



`DELTA IS JUST WEIGHING THETA, it is basically the version of the sum part in our algorithm (dot product = sum of all products and later, we divide by n (multiplying with alpha divided by n) so delta is just the weighed sum before we calculate the average error and correct it using alpha and subtracting from theta)` 
--> this was the key thought needed to understand one of the last barriers


`theta = gradient_descent(X,Y)`
--> the actual variables are calculated


plotting the data and our final function:
`ax = sns.scatterplot(x='population', y='profit', data=df)`

`plt.plot(X[:,1], X.dot(theta), color='r')`

`ax.set(xlabel='Population of City in 10,000s', ylabel='Profit in $10,000s', title='Training data with linear regression fit');`







------------------------------------------------------
### References
