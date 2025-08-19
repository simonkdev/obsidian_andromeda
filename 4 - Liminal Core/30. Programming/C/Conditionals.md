2025-08-18 15:35

Tags: [[C Language]]

------------------------------------------------

##### General:
They are basically the same as in JavaScript.

**Example:**

`if (number <= 5) {`
	`printf("I am bored. Here is the number: %d\n", number);`
`}`

##### Ternaries:

`int age = 20;`
`(age > 19) ? printf("Adult) : printf("Teen");`

##### Switches:

`int day = 4`
`char dayName[];`

`switch (day) {`
	`case 3: dayName = "WED";`
	`case 4: dayName = "THU";`
	`default:`
		`dayName = "other day";`
`}`

**HINT**: When you wanna do a switch with Strings, you have to use `strcmp()` and `if..else` chains because switches only support int-like data types


------------------------------------------------------
### References
https://quickref.me