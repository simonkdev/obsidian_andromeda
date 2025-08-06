2025-08-06 12:44

Tags: [[JavaScript]] 

------------------------------------------------
##### Overview:
Surprisingly, the syntax are very similar to nix syntax. Here is an example tho:

`const apple = {`
	`color: "Green", `     <-- comma seperates key-value pairs
		^
values are assigned with ":" instead of "="
	`price: { bulk: "3€/kg", box: "5€/kg" },`
// values can be list of own key-val pairs
	`average_weight_kg: 5`
				       ^
			last key usually does not have a comma,
			but it doesnt give a fucking shit if there is one
}

deleting keys:
`delete apple.color"

assigning multiple properties at once:
`const {color, average_weight_kg : avg_kg} = apple`
								   ^
						renaming a property

variable as value makes the variable name the key:
`const name = "Tom"`
`x = {`
   `name,`
   `size = 4,`
`}`

`console.log(x) --> { name = Tom, size = 4}`

you can also access keys like an index:
`person.hobby === person[hobby]`

values are mutable, therefore functions can modify them:
`origObj = {color: "green"}`
`makeAesth(obj)`
`{`
	`obj.color = "purple"`
`}`
`console.log(obj.color)` ---> will output "purple"

you can also design methods like functions but without the keyword:

`cat = {`
	`name: "Pipe"`
	`age: 22`
	`fall() {`
		`console.log(´*Metal Pipe falling*, its name was ${this.name}´)`
	`}`
`}`

you can also create Objects with functions that have parameters:

`function createCat(name, age) {`
	`return {`
		`name: name,`
		`age: age,`
		`breed: "Cat."`
		`bark() {`
			`console.log('Woof...\n\rWait a minute' )`	
		`}`
	`}`
`}`

you can create two methods, one as getter, one as setter, that have the same name. The setter will be invoked by assignment and the getter by referencing (e.g. console.log()):

const myCat = {
	name = 'Polka Dot',
	get name() {
		return this.name
	},
	set name(newName) {
		this.name = newName
		console.log(´The cat's new name is ${this.name}´)
	}
}

console.log(myCat.name)

myCat.name = 'Coca Colaaa'





------------------------------------------------------
### References
https://quickref.me/javascript