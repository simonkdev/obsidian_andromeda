2026-05-23 22:34

Tags: [[machine learning]] [[neural networks]] [[gradient descent]] [[back propagation]]

------------------------------------------------


### "Unrolling" the network
This means treating the network as a traditional feedforward deep learning network. Each layer corresponds to a time step. 

Ergo:
- Layer 1 produces S_1
- Layer 2 produces S_2
(and so on..)
- Layer T produces S_T
- Output Layer produces Y_hat

This means we can basically use backprop like we are used to (see [[back propagation]]).




------------------------------------------------------
### References
https://www.youtube.com/watch?v=0XdPIqi0qpg