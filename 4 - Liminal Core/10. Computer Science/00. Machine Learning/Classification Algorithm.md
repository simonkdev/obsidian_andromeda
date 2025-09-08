2025-09-08 10:47

Tags: [[machine learning]] [[Supervised Learning]]

------------------------------------------------

##### Overview:
A classification algorithm works similar to a linear regression (s.below). The difference is the amount of possible outputs: While a regression has infinitely many outputs (e.g. any integer for house prices), a classification has a very small number, referred to as categories or classes. 
Often, these categories have numeric representatives (in example below: 0 = not cancer ; 1 = cancer), but they can also be non-numeric.

##### Example:
A classification model that is supposed to determine whether a lump is cancerous or not will have two different possible outputs: "cancerous" and "not cancerous"

##### Graphical:
If described as a graph, the model determines one or more boundaries which decide which output is correct. The example above with two inputs and two outputs would probably look like this: 
![[2025-09-08-110020_hyprshot.png]]
*HINT: The boundaries are often not linear or 2-D, this is strongly simplified!!*
##### Probabilities:
Most classification models work by first suggesting a probability for each class / category and then decide which one is the ouput based on (a) context-defined rule(s). In the example above, it might be 70% cancer and 30% not cancer. The rule could then be to pick the highest one, resulting in a positive diagnosis.


------------------------------------------------------
### References
[[Regression Algorithm]]
https://chatgpt.com/c/68be9f50-ba70-8325-acf6-5239b75d5a0c