2026-01-23 09:45

Tags: [[computer science]]

------------------------------------------------

### General:
A sliding window operation means iterating over  [[4 - Liminal Core/30. Programming/Assembly/linear data structures|linear data structures]]  bit by bit, continuously reusing previous compute results. 
For example, if you were computing the sum of an array, with a sliding window operation with a fixed-size window of size two, 
you would go in steps of one position and add the sum of the current two values in the window to the previous sum 
(of course, you have to avoid adding values twice, so you subtract those first).

### Fixed-size window:
Best explained with an example:

List: `[2, 4, 6, 8, 10]`  
Window size: `2`

Windows as they slide:
`[2, 4, 6]`
 `[4, 6, 8]`
 `[6, 8, 10]`

If you were finding the **sum**:

First window sum = `2 + 4 + 6 = 12`
Slide right: subtract `2`, add `8` → `18`
Slide right: subtract `4`, add `10` → `24`

### Variable-size window:
In this case, the window gets bigger or smaller depending on a condition.
For example, if you were looking for the longest substring in an array without repeating characters, 
the window's size would get smaller / stop growing upon containing one character twice.




------------------------------------------------------
### References
https://chatgpt.com/c/697334ae-abf8-832d-87c1-30b6bf4143a8