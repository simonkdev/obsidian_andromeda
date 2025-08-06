2025-08-06 16:43

Tags: [[JavaScript]]

------------------------------------------------

##### Methods:
- `GET`
	--> receives data
- `POST`
	--> sends data

##### Fetch:
`args = { method, headers, body}`  <-- object with available args, if left empty or not passed as function argument below uses standard values

`fetch(url, args // optional)`
`.then(function (response) {`
	//what to with the response, usually just returning it as a json, response.ok is a boolean that is true if the fetch succeeded
	`if (response.ok)`
	`{`
		`return response.json()`
	`}`
	`throw new Error(Request failed, response: ${response})`
`})`
`.then(function(data) {`
	//what to do with the json data from the previous then
`})`
`.catch(function(error) {`
	// handles an error in case it arises anywhere before here
`})`




------------------------------------------------------
### References
