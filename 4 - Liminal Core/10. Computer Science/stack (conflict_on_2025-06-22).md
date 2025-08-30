2025-03-08 12:09

Tags: [[computer science]] [[data types]] [[programming]] 

------------------------------------------------
#### Definition: 

-> linear data structure which only allows changes and access at the end ("Top of the Stack"). Is declared with a size.

Example in real life: Stack of books or coins, you can only place or take at the end. You can also only read the book on the top as the others are covered

HINT: Can store multiple different data types, unlike [[array]]

#### Stack as an abstract data type

When defined as an ADT (abstract data type), we only want to know the operations concerning it from the user perspective

--> Details in der Implementierung sind uninteressant, nur die Arten an Aktionen die wir machen können

#### Primary operations

push(data):
	Inserts data onto the stack

pop():
	deletes last element added (data on top)

top():
	returns last element added without deletion

size():
	returns number of elements that are part of the stack

isEmpty():
	returns TRUE if it´s empty, FALSE if it isn´t

isFull():
	returns TRUE if defined size has been reached (if size() equals the defined size), FALSE if it hasn´t








------------------------------------------------------
### References

YouTube Video: https://www.youtube.com/watch?v=I37kGX-nZEI
Topic: [[linear data structures]] 
Important: [[abstract data type]] 

