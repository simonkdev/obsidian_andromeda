2025-08-19 15:37

Tags: [[C Language]]

------------------------------------------------
##### Arithmetic:
`+, -, *, /, %, ++, --`
--> the usual

##### Comparison:
`==, !=, >, <, >=, <=`
--> also the usual

##### Logical:
`&&` --> and (both true --> true)
`||` --> or (at least one true --> true)
`!` --> not (inverts boolean evaluation)

##### Bitwise: 
`---` `&` 
"AND" --> goes through both integers in binary form and forms a new one with the same amount of digits, being 0 if they are not the same and 1 if they are, e.g.:
![[Pasted image 20250819154538.png]]

`--- |`
"OR" --> same as `&` but only one of both digits has to be 1, e.g.:
![[Pasted image 20250819154751.png]]

`--- ^`
"XOR" --> same as `&` and `|` but returns 1 only if the digits are different, e.g.:
![[Pasted image 20250819154927.png]]

`---` `~`
"NOT" --> inverts all digits of a given number in binary, e.g.:
![[Pasted image 20250819155053.png]]

`---` `<<`
"Left Shift" --> shifts bits to the left, adding zeros on the right. Each shift is equivalent to multiplying by two, e.g.:
![[Pasted image 20250819155208.png]]

`---` `>>`
"Right Shift" --> shifts bits to the right; for unsigned integers, zeros are added on the left (equivalent to dividing by 2 for each shift), for signed integers, it depends on the compiler
![[Pasted image 20250819155427.png]]

Mostly used for cryptography and efficient arithmetic operations.


------------------------------------------------------
### References
https://chatgpt.com/c/68a47f83-d698-8333-99bf-def12c983cd5
https://quickref.me