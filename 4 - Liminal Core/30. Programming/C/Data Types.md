2025-08-18 12:08

Tags: [[C Language]]

------------------------------------------------
##### Basic types:

`int` --> integer
`float` --> small decimal number (kl. anzahl an stellen)
`double` --> big decimal number (gr. anzahl an stellen)
`char` --> character
`string` --> not directly available, written as 
			`char name[] = "string"`

##### Derived data types:

`array` --> list of elements of the same type
`pointer` --> stores memory addresses
`union`--> struct but shares memory
`enum` --> like in python (indexed array)

##### Modifiers:

`short` --> makes size smaller
`long` --> makes size bigger

`signed` --> allows positive and negative values
`unsigned` --> only allows positive numbers

##### User-defined:

---> `struct`:

like an object in JS, it creates a custom data type with multiple variables of user-chosen variables that have different types
**Example:** 

`struct Student {`
	`int id;`     <-- 4 bytes
	`char name[50];`    <-- 50 bytes
	`float gpa;` <-- 4 bytes
`}`;
`int main() {`
	`struct Student s1 = {101, "Alice", 3.8};`
`}`

total size of `s1` in memory: 58 bytes


---> `union`:

like a `struct`, but way more memory efficient as only the current value is loaded at once. Therefore, the reserved memory space is only as big as the biggest value in the object.
**Example:**

`union data {`
	`int i;` <-- 4 bytes
	`float f;`  <-- 4 bytes
	`char str[20];` <-- 20 bytes
`};`

`int main() {`
	`union Data d;`
	`d.i = 42` <-- stores value in memory
	`d.f = 3.14` <-- overwrites memory slot, value of `d.i` can no longer be accessed
`}`

total size of `d` in memory: 20 bytes

---> `typedef`:

lets you assign an alias to complex declarations.
**Example:**

`typedef unsigned int uint;`
`uint age = 25;`


---> `enum`:

creates a collection of named constants.
**Example:**

`enum Day { MON, TUE, WED, THU, FRI, SAT, SUN };`

`int main() {`
	`enum Day today = WED;`
	`if (today == WED)`
		`printf("It is ze middel of ze wiek");`
`}`


------------------------------------------------------
### References
