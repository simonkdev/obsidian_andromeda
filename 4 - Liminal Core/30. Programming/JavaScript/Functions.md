2025-08-05 15:09

Tags: [[JavaScript]] 

------------------------------------------------

##### General: 
nothing special, mostly the same as java with some exceptions: 

`function sayHello(name) {`
  `return "Hello ${name}, enjoy your next 24 hours!"`
`}`

you can also declare like this ("anonymous functions):
						declare standard value (if left empty, use this, not limited to this notation)
								v 
`const sayHello = function(name = "Simon") {`
`return "Hello ${name}, enjoy your next 24 hours!"`
`}`

or this: 

`const sayHello = (name) => {`
  `return "Hello ${name}"`
`}`

you can assign a variable a function and then call the variable like a function:

`plusFive(numer) {`
	`return number + 5;`
`}`

`f = plusFive;`

`f(9) // = 15`

You can also embed functions as so-called "Callback functions":

`function isEven(n) {`
	`return (n % 2 == 0) ? true : false;`
`}`

`function divideIfEven(evenf, num, div) {`
	`if evenf(num):`
		`return num / div;`
	`throw new Error("not even")`
`}`




------------------------------------------------------
### References
https://quickref.me/javascript