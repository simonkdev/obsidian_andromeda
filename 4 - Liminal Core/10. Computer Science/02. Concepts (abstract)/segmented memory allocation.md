2025-08-19 14:07

Tags: [[computer science]]

------------------------------------------------
##### Overview:
in a segmented memory section, processes fill up the physical memory in a linear manner, going from the first to the last memory cell in order.

![[Pasted image 20250819140843.png]]

##### Loading a process into full memory:
in order to load a program into full memory, an inactive sub-process of another program is moved to the swap file on the hard drive. This process has to be equal or  
greater in size than the program that is to be loaded. 

##### Fractional memory space:
unloading a sub-process of a program leaves behind empty space. This empty space can be used for another process. however, a process always needs a contingent empty space equal or greater than its own size to be able to load. This is because in segmented memory allocation, processes are atomic, meaning they can not be split into smaller parts (Programs can be split into processes but processes can not be split further).

##### Summary:
- segments are swapped between hard drive and memory as needed
- program segments correspond to sub-processes such as procedures or functions
- segments greater or equal in size have to become idle and then be unloaded onto the drive to free up space for other segments
- Segments are atomic, they cannot be split
- if the memory is fractional, meaning there are gaps between segments, these are individual segments and can not be used for one bigger process, as they require a contingent free segment
- the OS knows start and size of each segment in physical memory
- segments can be pushed together to close the gaps and combine them into bigger spaces to allow bigger segments to be loaded




------------------------------------------------------
### References
