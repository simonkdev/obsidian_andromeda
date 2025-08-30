2025-08-27 15:33

Tags: [[machine learning]]

------------------------------------------------

##### Overview:
"Supervised machine learning" refers to algorithms that learn x to y (input to output) mappings by being given example inputs with the correct "answers" (outputs). Over time, the model makes more and more accurate predictions of what the output y should look like.

##### Specific application:
![[Pasted image 20250827173519.png]]
In this case, the model is given a dataset with two values: house size and price. Based on these combinations, it has to predict the output (more specifically, the price) for a new house size. 
The model plots the dataset as shown above, and an algorithm is used to predict the output based on the results of the training stage (where the model was given the dataset). Depending on which algorithm is used, the resulting graph (blue line) is drawn to make a prediction of where the new value lies.

> In summary, you could say it uses a set of x and y values to plot a function graph and determines the position of the new x value on this graph to predict the corresponding y value. The shape of the graph is determined by the algorithm used to train the model

*HINT: The model does not literally draw any graphs, but rather saves mathematical parameters that approximate the mapping from size to prize.*

##### Examples:
- E-Mail spam filter
- STT (Speech to text / speech recognition)
- Social Media algorithm (input: combination of video and user, output: positive / negative engagement)
- Autonomous driving (input: image, radar info; output: position of other cars in proximity)
- visual inspection filter (defect tech)


------------------------------------------------------
### References
https://chatgpt.com/c/68af278f-52f4-8323-bcd6-35902a417688
https://www.youtube.com/watch?v=sca5rQ9x1cA&list=PLkDaE6sCZn6FNC6YRfRQc_FbeQrF8BwGI&index=4