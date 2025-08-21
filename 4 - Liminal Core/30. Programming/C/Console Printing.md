2025-08-18 14:53

Tags: [[C Language]]

------------------------------------------------
##### General:
method: printf("string", val1, val2, etc.)
--> requires stdio.h library

##### Printing variables:
there are format specifiers for different types of variables:
	`%d or %i --> signed decimal int`
	`%u --> unsigned decimal int`
	`%o --> unsigned octal int`
	`%x --> unsigned hexadecimal int lowercase`
	`%X --> unsigned hexadecimal int uppercase`
	`%f --> float`
	`%c --> char`
	`%s --> string`
	`%lf --> double (long float)` 
	`%p --> hexadecimal pointer address`
in case a literal % character is needed, it is written as `%%`

*HINT:* a pointer is 8 bytes, a hexadecimal int is 4. so if you print a pointer with the format specifier for a hexadecimal, it only outputs the first 4 bytes of an 8 byte value, making the output wrong.

Example:

`int main() {`
	`long long big = 1234567890123;`
	`double pi = 3.14159;`
	`char ch = 'A';`
	`char str[] = "Hello";`

	`printf("Big number: %lld\n, big);`
	`printf("Pi: %lf\n", pi);`
	`printf("Character: %c\n", ch);`
	`printf("String: %s\n")`

	`return 0;`
`}`

##### Modifiers:
Again, every one of the format specifiers can be extended with a modifier. Valid are:
`l` --> long
`h` --> short
and the respective doubled ones.

##### Alignment and Spaces:
You can create a table-looking output with these modifiers:

`printf(%-9d %-9d %-9d \n)`

broken down:

`%d` --> output signed decimal int
`-` --> align to left (without, it would be to the right)
`9` --> occupy 9 characters (if less, it is filled up with spaces)

therefore, each of the printed variables is printed aligned to the left, then the remaining of the 9 slots are filled with spaces, and then there is the next number. 


------------------------------------------------------
### References
https://quickref.me/c
[[Variables]]
