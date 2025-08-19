2025-08-18 15:18

Tags: [[C Language]]

------------------------------------------------
##### General:
There are no strings. It does not exist. You gotta make a `char` array lol. 
Done like this: `char greetings[] = "Hello World!"`
But the variable name acts like a pointer in functions, which is important for [[User Input]]

##### Modifying:
The nice thing is: you can modify it like an array :)
`greetings[0] = 'J';`
`printf("%s", greetings);` //"Jello World"

##### String literals:
you can make a string read-only by making it a string literal and just defining a pointer for it, making it act as a pointer all the time, not just in functions.
The pointer contains the address for the first character of the string and `printf` will print all characters that occur until the next `\0` character in memory.

`char *greetings = "Hello";`
`printf("%s", greetings);`


------------------------------------------------------
### References
https://quickref.me/c
[[Variables]] [[4 - Liminal Core/30. Programming/C/Data Types|Data Types]] 