2025-09-26 17:03

Tags: [[machine learning]]

------------------------------------------------

##### Overview:
We can enhance multiple linear regression by adding feature engineering to make curved fits to a model. 
To accomplish this, we take an existing feature and create a new one using one of the methods below:

##### Squared feature:
you can just add a new feature which is the same but squared. This is very simple but the curve will fall down for higher numbers (Parabel) which is not ideal for most use cases.
Keep in mind that feature scaling is very important as the size of the input values gets exponentially bigger.

##### Cubic features:
to solve the falling curve problem of squared features, you can just make them cubic (³).

##### Square root:
you can also use the square root of your feature, which has a curve that rises slower than the cubic one but still never goes down.

##### Combining / higher exponents:
You can combine as many features as you like, with no limitations in the size of the exponents. Just remember to normalize them after so the algorithm still converges quickly.

##### Implementation:
In pract<ice, polynomial regression is basically the same as linear regression except for adding features in the beginning. Also, if you want to plot it, do not use a line plot but rather a scatter-plot, as most of the time the data will not be in a sorted order and the line plots will zig-zag all over the place.






------------------------------------------------------
### References
