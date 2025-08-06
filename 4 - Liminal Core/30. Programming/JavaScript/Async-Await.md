2025-08-06 16:23

Tags: [[JavaScript]]

------------------------------------------------
##### Overview:
If we need a value from a pending [[Promises]] and need it in a synchronous function, we can define the function as an `async` function and use `await` to pause execution until we get a value from the Promise. If the Promise already has one, we just move on. This is great for error prevention.

##### Syntax:

`function random() {`
	`return Promise.resolve(1)` <-- returns a promise that takes the value 1 when resolved but has no executor meaning it resolves instantly
`}`
`async function run() {`
	`const val = await random()`
`}`


------------------------------------------------------
### References
https://quickref.me/javascript