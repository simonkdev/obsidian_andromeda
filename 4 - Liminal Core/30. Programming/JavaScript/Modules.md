2025-08-06 13:58

Tags: [[JavaScript]]

------------------------------------------------

#### Overview:
Every module is just a .js file that presents methods for others to use. They are imported like this:

`const myMath = require('./myMath.js')`
`// accessed via e.g. myMath.duplicate(x,y)`

or this:

`import {duplicate, multiply, subtract } from './myMath.js'`
`// accessed like functions in the same file`
##### Normal:
normal javascript modules can export functions like this:

`function multiply(x,y){`
    `return x * y`
`}`
`function duplicate(x){`
    `return x * 2`
`}`

`export {`
	`multiply,`
	`duplicate`
`}`

or this:

`export function subtract(x,y) {`
	`return x-y`
`}`

##### Node Modules:
if you intend to use them as nodejs modules, you export like this:

`function multiply(x,y){`
    `return x * y`
`}`
`function duplicate(x){`
    `return x * 2`
`}`

`module.exports {`
	`multiply,`
	`duplicate`
`}`





------------------------------------------------------
### References
https://quickref.me/javascript