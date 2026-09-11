2025-08-19 13:45

Tags: [[computer science]]

------------------------------------------------

##### Overview:
paged memory allocation uses both logical and physical memory. the physical memory is maintained with a [[segmented memory allocation]], while the logical memory is split into pages. These pages all have the same size and can contain one program, part of a program, or more than one program. The size varies depending on the OS, but many use 4096 bytes (4 kilobytes). the OS maintains a page table which maps segments from the physical memory to pages in logical memory.

##### Splitting processes:
programs (including their processes) are split into pages. This includes partial pages if the required space can not be evenly divided by the size of the pages.

##### Addressing memory in pages:
Every program acts as if the entire physical memory belonged to them. Meaning each of them start their memory at address `0x0` and every memory address they access is in reference to this. 

Memory addresses used by a program are relative to the beginning of its logical memory. In real memory, each page of logical memory is stored in a segment. 
If you convert a memory address from [[hexadecimal notation]] to decimal notation, it describes the offset from address `0x0` (in logical memory) in bytes.
These offsets can then be utilized to determine the page which contains this address as well as the location within the page. The location within the page is then translated into the real address using parts of the [[CPU]] and accessed by the [[CPU]] executing the given instruction.

![[Pasted image 20250819143741.png]]


------------------------------------------------------
### References
https://www.youtube.com/@ComputerScienceLessons
https://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/9_VirtualMemory.html
https://chatgpt.com/c/68a45f00-99e8-8327-9df2-150f6afde99b