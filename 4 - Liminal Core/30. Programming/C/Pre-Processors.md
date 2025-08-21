2025-08-21 11:23

Tags: [[C Language]]

------------------------------------------------
##### Available preprocessors:

- `#define` / `#undef`:
	define / undefine a macro; for example:
	`#define MAX_FILE_SIZE 42`
	`#define LINE_LENGTH 58` 
	these are now global constants.
	You can also declare functions as a macro, for example:
	`#define square(x) ( (x) * (x) )`
	If a macro is too long to fit into one line, you use the continuation operator `\` to expand into the next line:
	`#define message_for(a,b) \
		`printf(#a " and " #b ": We love you!\n")`
	As you can see above, if a macro parameter is needed as a string constant, you use the `#` prefix.
- `#include`:
	include a source code file, if from system library, you use `<name>`, if in local directory, you use `"name"`. 
- `ifdef` / `ifndef`:
	checks if a macro is defined or not.
- `if, else, elif, endif`:
	start, decide, decide, end a conditional compilation block. For example:
	`#if MODE == 1`
		`printf("Hello");`
	`#elif MODE == 2`
		`printf("Bye");`
	`#else` 
		`printf("You son of a bitch");`
	`#endif`
- `#pragma message(" ... ")`:
	sends a message to compiler output
- `#error`:
	raises an error at compile-time (e.g. unsupported Macro value)

##### Predefined macros:

- `__DATE__`:
	the current date, in format `"MMM DD YYYY"`, e.g. "Jan 14 2025" (`char array / string`)
- `__TIME__`:
	The current time, in format "`HH:MM:SS`", e.g. "14:35:21" (`char array / string`) 
- `___FILE__`:
	Current file name, also as `char array` / `string`
- `__LINE__`:
	Current line number, a decimal constant
- `__STDC__`:
	a constant indicating the standard of your compiler, useful for portability and compatibility

##### Extras:
- the `defined()` operator: 
	by using defined() in a conditional block, you can check if a macro is defined. Inverting via `!` is supported.





------------------------------------------------------
### References
https://quickref.me/c