2025-08-19 11:58

Tags:  [[C Language]]

------------------------------------------------
##### Overview:
We use the `scanf` method from the `stdio.h` library. It takes two arguments:  The format specifiers (same as in [[Console Printing]]) and the memory location of where it should write the received value. 
For most data types, this location is received by using the prefix "&", for example:
`scanf("%f", &price);`
However, since the names of arrays (and therefore strings) are already pointers to their location (outlined in [[Strings]] and [[4 - Liminal Core/30. Programming/C/Arrays|Arrays]]), you leave out the prefix:
`scanf("%s", string);`






------------------------------------------------------
### References
