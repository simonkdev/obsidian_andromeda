2026-01-22 12:11

Tags: [[machine learning]] [[ML architectures]] 

------------------------------------------------

### General:
contrary to the [[multilayer perceptron (MLP)]] architecture, a CNN specifically utilizes spatial relationships between single features
to detect patterns and shapes. It uses several filters to look for patterns, which get applied to all areas of the input.

In the context of images, this means it looks for shapes like curves or right angles by applying the same weights to all areas of the image, unlike an MLP, 
which uses new weights for every single bit of area. This makes them more efficient in learning.

They still learn through backprop and contain [[convolutional layers ]] and [[pooling layers]]. 
At the end, a fully connected layer ( basically a very small [[multilayer perceptron (MLP)]]) performs classification.




------------------------------------------------------
### References
https://chatgpt.com/c/697200ec-009c-8396-aa54-58b4a8e2c9a7