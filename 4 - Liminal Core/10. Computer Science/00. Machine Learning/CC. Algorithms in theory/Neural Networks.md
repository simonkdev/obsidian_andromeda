2025-10-21 16:13

Tags: [[machine learning]] 

------------------------------------------------
##### Structure / general:
Put simply, a neural network consists of an input vector (input layer), an output value (output layer) and one or more hidden layers.
These hidden layers contain neurons (simple models such as a [[logistic regression]]) which turn the activation vector 
(=outputs of all neurons of the previous layer) into a new number (= output = activation). 
This new number together with all other activation values of the layer forms the input vector for the next layer.

The amount of neurons within a layer and the amount of layers in a network depend on the [[neural network architecture]]. 
Unlike in a [[polynomial regression]] using [[Feature Engineering]] for more precise outputs, a neural network decides which features are needed on itself, 
making it incredibly powerful for big datasets. 

**HINT**: Sometimes, a neural network with multiple layers is called a "multilayer perceptron", which is just referring to a neural network with
multiple layers. OxO

##### Mathematical layer:
Each Layer can be represented as one vectorised function:
$$z^{[l]} = W^{[l]}a^{[l - 1]}+B^{[l]};    a^{[l]} = g(z^{[l]})$$
where:
- $W$ is the weight matrix of size (rows = count of neurons in the layer, columns = row count of previous' layers activation value vector (or input vector in the first layer))
- $B$ is the bias matrix with size (amount of neurons, 1)
- $a^{[l]}$ is the activation value vector of the corresponding layer $l$
- $f()$ is the nonlinear activation function (e.g. the sigmoid function)


**Forward Propagation**:
refers to the action of data passing through a neural network


------------------------------------------------------
### References
[[logistic regression]] [[Regression Algorithm]] [[Real-World UVLR]]
https://www.youtube.com/watch?v=ggWLvh484hs&list=PLyoNSC4BT4eVpykPF0Yx8C1Zs50XtD17L
