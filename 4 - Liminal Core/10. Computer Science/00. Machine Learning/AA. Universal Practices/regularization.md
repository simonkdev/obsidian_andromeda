2025-10-14 15:33

Tags: [[machine learning]]

------------------------------------------------

##### Overview:
If you have a model that overfits due to having too many polynomial features, 
one way to fix this is implementing regularization. Essentially, you are giving your
algorithm another hyperparameter (like the learning rate) which causes it to keep the parameters very small.
**(b is not regularized)**
This picture explains it quite well:
![[2025-10-14-154830_hyprshot.png]]


##### Cost function with implemented regularization:
$$J(\vec{w}, b) = \frac{1}{2n}\sum^n_{i=1}(f_{\vec{w},b}(\vec{x}^{(i)}) - \vec{y}^{(i)})² + \frac{\lambda}{2n}\sum^m_{j=1}w_{j}²$$
(n = anzahl beispiele, m = anzahl features)
##### Regularized gradient descent:
Essentially, it looks like this:
$$\theta = \theta - \alpha \left[ \frac{1}{n}X^T(X\theta-Y) + \frac{\lambda}{n}R\theta\right]$$
Where R is just a bias vector to exclude b ($\theta_0$) from regularization. It looks like this: $R = [0, 1, 1, 1, ... 1]$ with shape $(n,1)$
(In the theoretical equations a diagonal matrix is used (all zeros with a diagonal line of ones and $R[0,0] = 0$) because it makes mathematical derivation easier)

##### What it does:
In addition to the normal gradient descent update, we also subtract $\alpha \frac{\lambda}{m}\theta_j$ from $\theta_j$, where $\alpha$ is a very small number (like 0.01), lambda is a small number (like 1) and m is the number of features, e.g. 50. Therefore, $\alpha\frac{\lambda}{m}$ is a very small number, e.g. 0.00002 and multiplying it with $\theta_j$ and then subtracting that from $\theta_j$ is like multiplying it with a number close to 1. Since we do this every update, we continuously shrink $\theta$ over time, making it way smaller overall. The bigger $\lambda$ is set, the smaller $\theta$ will be at the end, because the result of $\alpha\frac{\lambda}{m}$ will be bigger and $\theta$ shrinks more every update.


##### Adapting for logistic regression:
All you have to do is exchange f(x) with sigmoid(f(x)) and you are good to go!





------------------------------------------------------
### References
https://chatgpt.com/c/68ee5818-9a24-8325-95e2-e3f0921aa9c6
https://www.youtube.com/watch?v=jhrrw8Iuus0&list=PLkDaE6sCZn6FNC6YRfRQc_FbeQrF8BwGI&index=40