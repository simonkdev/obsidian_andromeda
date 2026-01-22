2025-11-04 10:32

Tags: [[machine learning]] [[neural networks]] [[gradient descent]]

------------------------------------------------



##### Steps:
1. calculate predicted value with given input, store 
	(see [[neural networks]])
2. calculate derivatives for each parameter in each neuron on each layer, assemble in a matrix (matrix of gradients)
	use the derivative of the cost function with respect to the current parameter, see below
3. update all parameters at once

##### Stupidly simple words:
if we leave out activation functions and biases (so the entire network is linear with only W and X), we can say:
> Slope of neuron in level 2 equals slope of neuron in level 3 dot product parameters of level 3.

If we add activation back in, it mostly stays the same as above, except we elementwise multiply with 
the result of the sigmoid derivative. To calculate that result, we need the result of the current neutron with the 
"old" parameters. 
Here is the sigmoid prime function:

`def sigmoid_prime(x):`
    `s = sigmoid(x)`
    `return s * (1 - s)`

For the output layer, since we don't have a higher layer, we use the MSE (mean squared error) instead.




##### Derivative calculation:





------------------------------------------------------
### References
https://www.youtube.com/watch?v=qzPQ8cEsVK8&t=120s
https://www.youtube.com/watch?v=-zI1bldB8to