2026-08-12 11:36

Tags: [[machine learning]] [[Reinforcement Learning]]

------------------------------------------------

### Alternate names
Monte Carlo policy gradient algorithm, REINFORCE algorithm, Vanilla policy gradient, Vanilla REINFORCE, Likelihood-ratio policy gradient, Score-function estimator, log-gradient trick

### General
The policy gradient method training algorithm for reinforcement learning learns a policy (some form of regression or neural network) by producing a total loss using sampling. 

During one sampling run, multiple episodes are run and recorded at every timestep ("trajectories"). 
These episodes are then processed to get total cumulative rewards for every state-action pair, which are further put into an equation yielding the Loss contribution of every one of these pairs. 

The loss contributions are summed up into the total error of the current policy, which the learning engine corresponding to the type of the policy uses as its error (e.g. back propagation for an MLP). 

A detailed diagram of the learning process is here:
[[Drawing 2026-08-12 11.36.54.excalidraw]]


------------------------------------------------------
### References

https://chatgpt.com/c/6a7c3b94-7d70-83eb-94ef-927b0c672c7c
https://www.youtube.com/watch?v=VnpRp7ZglfA&t=1027s
