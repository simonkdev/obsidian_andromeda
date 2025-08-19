2025-08-19 11:30

Tags: [[C Language]]

------------------------------------------------
##### Overview:
An `enum` is an int-compatible (meaning stuff like `printf` and `scanf` use the integer formats for it) data type that can have the values you assign to it when it is defined.
The values are not accessed by their name or value but rather by their index, which can be assigned by you. If the index is not assigned, it is increased from left to right. 

*Examples:*
						automatically assigned to 5 because of auto-increment
									v
`enum week {Mon = 2, Tue = 9, Wed = 4, Thu};`

`enum week day;` 
	   	  ^ 
a variable with the valid values 2, 9, 4 and 5 

Furthermore, you could write a custom type `weekday` using `typedef` ([[4 - Liminal Core/30. Programming/C/Data Types|Data Types]]) and declare like this:

`weekday today;`




------------------------------------------------------
### References
https://quickref.me