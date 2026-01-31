2025-09-09 10:06

Tags: [[C Language]] [[programming]]

------------------------------------------------

##### Overview:
Structures in C work similar to classes in Java if you took away their functions. They have their own variables and therefore reference a collection of variables, but they do not have functions of their own.

##### Declaring and Instantiating:
Declaring a new structure looks like this:

`struct myStructure {`
	`int anyInt;`
	`char anyLetter;` 
`};`

And creating an object of that structure like this:

`// With assigning variables`
`struct myStructure s1 { 13, 'B' };`
`// Without assigning variables`
`struct myStructure s2;`

##### Modifying values:
You can modify any value like an attribute in Java:
`s1.anyInt = 234;`
Except for strings, which you have to do like this:
`strcpy( s1.aString, "Something Something World Domination";`




------------------------------------------------------
### References
https://quickref.me/c
