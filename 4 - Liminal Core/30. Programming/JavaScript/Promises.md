2025-08-06 14:09

Tags: [[JavaScript]]

------------------------------------------------

##### Overview:
an object that waits for an asynchronous operation to finish and executes a function based on the outcome.

[[Synchronous-Asynchronous]]

##### Three States:
the three possible states for a promise are:
- **Pending**:
	--> The initial state that awaits failure or completion
- **Fulfilled**:
	--> The operation completed successfully, the promise has a value
- **Rejected**:
	--> The operation failed and the promise has a "reason" (an error)
once it changes from Pending to one of the others, you can not reverb it.

##### Creation:
you create it like you would expect:

`const p = new Promise([executor function])`
							^
					is called upon construction

ergo:

`const p = new Promise(function (resolve, reject) {`
	`// The executor goes here. It is called synchronously on creation of the promise. It is where you start the asynchronous process that determines the success or failure of the criteria`
	`if (//criteria) {`
		`resolve(value) // is called upon success, gives the promise the wanted value`
	`} else {`
		`reject(errorObj) // is called upon failure, gives the promise the wanted error` 
	`}`

`})`

`p.then(function_on_success(res) {  })` assigns a function that executes when the promise succeeds.

`p.catch(function_on_failure(err) {  })` assigns a function that executes when the promise fails.

##### Collective Promises:

`collect = Promise.all([promise1, promise2])
`collect.then(yay(res))`
--> synchronous operation that waits until all promises in the given array finish and then enters its own state.
Available "collectors" are:

- `.all`:
	--> on success returns an array of the success values of the given promises, fails as soon as one rejects and gives the reason
- `.race`:
	--> goes through the given promises and settles with the value or error of the first promise to fulfill. (returns whatever the fastest one returns)
- `.allSettled`:
	--> always fulfills and returns an array with one array for every promise that looks like this: `{ status: "fulfilled", value }` or this: `{status: "rejected", reason }`
- `.any`:
	--> succeeds with the value of the first to succeed and rejects only if all given promises reject 

##### Chaining Promises:

every single one of the operator methods above return a promise in the successful or failed state, meaning you can chain them like this:

`function executor(res, rej) {`
	`// Asynchronous operation`
`}`
`p1 = new Promise(executor)`

`p2 = Promise.all([p1])`
`p2.then(function () {console.log("hello there")}).catch(function (err) {throw new Error("The force is weak within this one)})`


------------------------------------------------------
### References
https://quickref.me/javascript