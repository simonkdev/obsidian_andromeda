2025-08-05 13:10

Tags: [[JavaScript]] 

------------------------------------------------

##### if / else if Statement:

`const isMailSent = true;

`if (isMailSent) {
`	console.log("Mail sent.")
`}`
optional:
`else if (!isConnectedToInternet) {`
	`console.log("please connect to the internet first")`
`}`
--> "Mail sent."


##### Ternary operator:
		decision based on result (left of ":" is in          case reference is true, right is false)
				v 
`result = (x == 1) ? true : false;`
            ^
	reference condition


##### Logical operators:
- ` true || false`:
	--> checks if at least one of the statements is correct, here it would return true
- `true && false`:
	--> checks if both are true, here it would return false
- **Comparisons**:
	the usuals: >, <, <=, >=, but equal is === if types should be kept in mind and == if they are neglible
- `late = true; opposite = !late;`
	--> sets to the opposite boolean value
- `null ?? "lol":
	--> returns right side if left side is null or undefined, else returns left side / "if this is null or undefined, return this"

##### switch Statement:
`const food = "fish";`

`switch (food) {`
	`case "steak":`
		`console.log("wtf Casey I thought you were vegan!!!!");`
		`break;`
	`case "salad":`
		`console.log("okay nice choice");`
		`break;`
	`default:`
		`console.log("well you aint gettin lucky tonight with that in your stomach")`
`}`



------------------------------------------------------
### References
https://quickref.me/javascript