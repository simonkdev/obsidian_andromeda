2025-08-06 16:39

Tags: [[JavaScript]]

------------------------------------------------

##### Overview:
very similar to python, syntax look like this:

`json = '{ age: 30}'`      <-- invalid json

`try {`
	`user = JSON.parse(json)`
	`console.log(user.name)`
`} catch (e) {`
	`console.error(Invalid, error given: ${e.message})`
`}`





------------------------------------------------------
### References
https://quickref.me/javascript