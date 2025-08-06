2025-08-06 13:47

Tags: [[JavaScript]]

------------------------------------------------

##### Overview:
Basically a mix of objects in JS and classes in Java.
you declare a `constructor()` method that is executed every time you do `new object_of_class()`:

`class Song {`
	`constructor(writer, release, length) {`
		`this.title = 'It is always the same Title.'`
		`this.writer = writer`
		`this.release = release`
		`this.length = length`
		`this.cancelled`         <-- undefined but exists
	`}`
	`play () {`
		`console.log(Playing now: "${this.title}" by "${this.writer}" !)`
	`}`
`}`



------------------------------------------------------
### References
https://quickref.me/javascript