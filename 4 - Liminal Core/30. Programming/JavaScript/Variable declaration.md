2025-08-05 12:07

Tags: [[JavaScript]]

------------------------------------------------
#### Keywords: 

###### `var`
- **Scope**: accessible in the function it is declared in (private function variables)
- **Re-Declaration**: allowed within the same scope (in the same function)
- **Position**: top of scope, initialized as undefined ( have to be declared on top, else they are undefined and return "undefined" when doing console.log)
- generally discouraged but usable
###### `let` 
- **Scope**: Block-scoped ( only in the { } block it is declared in)
- **Re-declaration**: no
- **Position**: has to be top of scope, else ReferenceError (like var but returns Error instead of undefined)
- preferred for changing but block-wide variables (e.g. screen size)
###### `const`
- **Scope**: block-scoped (like `let`)
- **Re-declaration**: no
- **Position**: has to be top of scope, else ReferenceError (like let)
- values can not be reassigned but the content of objects (e.g. the position in an array) can be modified
- **special addon**: *strict mode* --> prevents the modification of objects' contents: 
	`const arr Object.freeze([1, 3, 4])`
	--> returns immutable array
	

------------------------------------------------------
### References
https://quickref.me/javascript