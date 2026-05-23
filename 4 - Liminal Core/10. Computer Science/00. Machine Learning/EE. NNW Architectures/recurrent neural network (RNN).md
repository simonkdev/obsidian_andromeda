2026-05-14 20:50

Tags: 

------------------------------------------------

### Overview:
A recurrent neural network deals with inputs that have different lengths using feedback loops. Inputs are passed into them sequentially, meaning the first input, then the second etc. for any length. Every value except the last one runs through a feedback loop: by adding the outputs of the last hidden layer for one value to the bias term of the first hidden layer for the next value, all inputs for any length are incorporated. The weights and biases are shared across all inputs.

### Feedback loop weight 
The feedback loop is just a linear function without a bias term, meaning of the form $w * x_i$. This weight can be trained as well.

### The Vanishing/Exploding gradient problem
Every value is passed through the feedback loop very often (although indirectly). The first one, for example, gets passed through as many times as there are inputs. If the feedback loop weight is anything other than 1, the first input will either vanish (w<1) or explode (w>1). Same goes for the other inputs, decreasing as we come to the last one. This also means that not all inputs will be treated equally.


------------------------------------------------------
### References
