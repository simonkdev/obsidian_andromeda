2025-08-18 16:00

Tags: [[C Language]]

------------------------------------------------
##### General:
The syntax are very familiar, albeit a bit weird. Also, the variable name is a pointer to the arrays location in memory (specifically, the first element, and the last one is always "\0", which signals the end of the array)

##### Declaration:
`int myNumbers[] = {25, 50, 75, 100};`
or with hard-coded size:
`int myNumbers[4];`

##### Accessing:
`int firstNum = myNumbers[0];` // copying
`myNumbers[0] = 33`   // modifying
##### Traversing:
`for ( int i = 0; i < 4; i++) {`
	`printf("%d\n", myNumbers[i]);`
`}`


------------------------------------------------------
### References
https://quickref.me