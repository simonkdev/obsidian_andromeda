2025-09-08 20:40

Tags: [[mathematics]]

------------------------------------------------
##### Overview:
The capital sigma symbol represents a summation, which works like this: 
$$\sum_{i=0}^{n}i$$
i being the lower limit (starting point); n the upper limit and i the formula. This works the same as a for-loop in Java (oddly enough). In words, this means: for i from 0 to n, add the results of i. Or, as actual Java code:

`int result = 0;`
`for( int i = 0; i < n; i++) {`
	`result = result + i;`
`}`
`return result;`

The formula can be anything, even complicated stuff, as long as the index on the bottom is referenced.

------------------------------------------------------
### References
https://www.reddit.com/r/ObsidianMD/comments/17pt5kh/how_do_you_write_the_summation_symbol_with_the/
https://www.youtube.com/watch?v=KbvD6FlIJGU