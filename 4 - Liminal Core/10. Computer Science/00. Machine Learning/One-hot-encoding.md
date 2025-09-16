2025-09-15 15:00

Tags: [[machine learning]]

------------------------------------------------

##### Overview:
One-Hot-Encoding is a way to use a categorical input where numerical input is expected. For example, if one feature for a gradient descent algorithm is wether a person is hispanic, white or black, we can not encode them like this:
`hispanic = 0, white = 1, black = 2`
because the model will wrongfully believe that hispanic < white < black, which is misleading.
Instead, we use one column per category and, using binaries, determine if it is present or not:
	`race            |      hispanic     white      black`

	`hispanic       |             1         0          0`
	`white          |             0         1          0`
	`white          |             0         1          0`
	`black          |             0         0          1`
	`hispanic       |             1         0          0`
(before (left) -> after (right) )

##### Using pandas in python
Pandas has a very convenient method for this called `get_dummies(dataframe, affected columns)`
which returns the new Dataframe with encoded columns




------------------------------------------------------
### References
https://www.geeksforgeeks.org/machine-learning/ml-one-hot-encoding/
https://chatgpt.com/c/68c80f04-f840-8322-b855-241ea53958a1

