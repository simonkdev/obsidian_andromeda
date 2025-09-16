2025-09-11 10:50

Tags: [[Numpy]]

------------------------------------------------

##### Overview:
Numpy is a python toolkit that allows advanced mathematical computation.

##### Import/Export:
- `np.loadtxt('file.txt')` // `np.genfromtxt('file.csv',delimiter=' ')
	returns an array containing one array per row in the text / csv file. Each number separated by a space within the row will be a part of the array for that row (delimiter determines the separating character)


##### Arrays:
- `np.zeros(3) / np.zeros((3,4))`
	creates an array with all values zero with the specified dimensions. If one value is given, it returns a one-dimensional array with the parameter given as its length. If two values are given, the first one is the amount of rows, the second one the length of each row (number of columns). Also works with `np.ones`, only with ones.
- `np.eye(length)`
	creates a square matrix with the dimension `length` that has a diagonal line of ones ("identity matrix")
- `np.linspace(start, end, steps)`
	creates a `1D` array of numbers that are evenly divided between start and end. Length is defined by steps.
- `np.arange(start, threshold, step size)`
	creates a `1D` array of  values that go from start as close to threshold as possible without getting to it with the step size defined. Example:
	`np.arange(10,50,5) --> [10, 15, 20, 25, 30, 35, 40, 45]`
- `np.full((3,4),8) // np.full(2, 8)`
	same as `np.zeros` and `np.ones` except you choose the filler yourself (here: 8).
- `np.random.rand(6,7) // np.random.rand(4,5)*100`
	array of size specified in parentheses with random floats between 0 and 1 or the same floats multiplied by whatever factor you put after (matrix scaling)
- `np.random.randint(5, size=(2,3))`
	array of size specified by size with random integers from a range of the size specified by the first value. Here: 0-4

##### Inspecting properties:
`arr` = any `numpy` array
- `arr.size`
	returns number of elements
- `arr.shape`
	returns dimensions of arr in form of an array (--> `shape[0]` = rows; `shape[1]` = columns)
- `arr.dtype`
	returns type of elements
- `arr.astype(target type)`
	returns the array with elements converted to the type in brackets, e.g.:
	`np.full((2,6), 8).astype(np.float32)`
- `arr.tolist()`
	returns numpy array as python built-in array ("list")

##### Copy/sort/reshape:
`arr` = any `numpy` array
- `np.copy(arr)`
	returns copy of array without changing the original one
- `arr.view(target type)`
	returns copy of array with elements converted to the target type
- `arr.sort()`
	sorts the elements in each row from lowest to highest and returns none (Optionally with specified axis but that doesn't matter for now)
- `2D-arr.flatten()`
	flattens the given `2D` array by discarding rows and putting all elements into one simple array. Example:
	`arr = np.random.randint(1, 101, size=(4,5)).flatten()`
	`---> [70 47 16 12 49 71 88 92 64 98 94 60 80 55 55 42 92  7 43  7] `
- `arr.T`
	"turns" the array by turning rows into columns and columns into rows (returns new one)
- `arr.reshape(x,y)`
	returns reshaped array by shifting the values between rows. Specified size must be equal to current size of the array
- `arr.resize(x,y)`
	resizes the array into the specified dimensions and new elements are set to 0. If the size is smaller, elements will be discarded to reach new size, starting from behind (if size is 4 elements smaller, the last 4 are deleted)

##### Add/remove elements:
`arr` = any `numpy` array
- `np.append(arr, values)
	appends the values to the array
- `np.insert(arr,2,values)`
	inserts values before index 2 of arr
- `np.delete(arr,3,axis=0)`
	deletes row 3 of arr
- `np delete(arr,4,axis=1)`
	deletes column 4 of arr

##### Combine/split
`arr` = any `numpy` array
- `np.concatenate((arr1,arr2),axis=0)`
	adds arr2 as rows to end of arr1
- `np.concatenate((arr1,arr2),axis=1)`
	adds arr2 as colums to end of arr1
- `np.split(arr,3)`
	splits arr into 3 sub-arrays
- `np.hsplit(arr,5)`
	Splits arr horizontally on the 5th column







------------------------------------------------------
### References
https://quickref.me/numpy