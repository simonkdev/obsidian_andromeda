2025-08-05 15:33

Tags: [[JavaScript]]

------------------------------------------------
##### General:
Same as python, including index notation and granting the ability for different data types within one array. Does not 
##### Methods:

- `.push(item)` :
	--> Adds the item to the end of the array and returns the new array
- `.pop():
	--> Removes the last item and returns the removed item
- `.shift()`:
	--> Remove the first item, let everything else fall down one index
- `.unshift(item):
	--> Add item to the beginning of the list, everything else moves one index up and method returns the new array
- `(item or array).concat(item or array)`
	--> returns a copy of the array with item in front or at end of array (depending on position) without modifying original array
- `.map`((item) => { return (action to be done) }):
	--> iterates through the array, executes the action (or function) for every item/member and adds the returned value to an array, and returns the array when finished
- `.forEach`(item => { (action to be executed )}:
	--> iterates through the array and executes the action once for each item.
- `.filter( item => { return n (criteria, e.g. < 5)})`
	--> adds each item in the array that meets the criteria to an array and returns the array once done


------------------------------------------------------
### References
https://quickref.me/javascript
