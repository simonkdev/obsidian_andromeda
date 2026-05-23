2025-11-04 10:32

Tags: [[machine learning]] [[neural networks]] [[gradient descent]]

------------------------------------------------
### General idea:
For every weight of every neuron in the neural network, we record the derivative of the Loss with respect to that weight.  Then we take a step in the sinking direction of that derivative, ultimately making the Loss lower and the network more accurate.

### How we get each derivative:
The derivatives are recorded in one matrix per layer, with one row per neuron and one column per weight in that neurons' formula. Therefore we get one matrix for every layers' weight matrix. 
Since derivatives are basically just ratios, we can use the chain rule. It looks like this:
$$
\frac{\partial L}{\partial W_{out}} = \frac{\partial L}{\partial A_{out}} * \frac{\partial A_{out}}{\partial Z_{out}} * \frac{\partial Z_{out}}{\partial W_{out}}
$$
Or like this for the n-th layer:
$$
\frac{\partial L}{\partial W_{n}} = \frac{\partial L}{\partial A_{n}} *  \frac{\partial A_n}{\partial Z_n} * \frac{\partial Z_n }{\partial W_n}

$$

now that last part describes how strongly the weight matrix influences the output of the neuron, which is simply the activated output of the n-1 -th layer (when that activation gets bigger, the effect of the same coefficient you multiply it with also gets bigger). 

Now we can calculate the derivative of any parameter in any matrix by calculating those three partials, with the second one simply being the derivative of the activation function and the third one being the activation of the layer below. 

The first one simply describes the impact this layers' activation has on the final loss. Again, using the chain rule, it looks like this:
$$
\frac{\partial L}{\partial A_n} = \frac{\partial L}{\partial A_{n+1}} * \frac{\partial A_{n+1}}{\partial A_n}
$$
That last term is the relation between the activation of layer n+1 and layer n. Which is nothing more than the weight matrix of layer n+1 and its activation function! With that, this formula turns into this:
$$
\frac{\partial L}{\partial A_n} = \frac{\partial L}{\partial A_{n+1}} * \frac{\partial A_{n+1}}{\partial Z_{n+1}} * \frac{\partial Z_{n+1}}{\partial A_{n}}
$$
Now the last term describes the relationship between the n+1 -th layers' inputs and its outputs, which is simply the weight matrix of that layer.  The second term also is, like above, just the derivative of the activation function.

Putting it all together, the matrix of the derivatives of a neurons' parameters can be calculated like this:
$$
\frac{\partial L}{\partial W_{n}} = \frac{\partial L}{\partial A_{n+1}} * \sigma_{n+1}' * W_{n +1} * \sigma'_n *A_{n -1}
$$

(this is with disregard to dimensions and elementwise/dot products)




------------------------------------------------------
### References
https://www.youtube.com/watch?v=qzPQ8cEsVK8&t=120s
https://www.youtube.com/watch?v=-zI1bldB8to
https://chat.mistral.ai/chat/7641caaa-1f33-44f6-9d3c-72243889d78f
https://www.youtube.com/watch?v=tIeHLnjs5U8
