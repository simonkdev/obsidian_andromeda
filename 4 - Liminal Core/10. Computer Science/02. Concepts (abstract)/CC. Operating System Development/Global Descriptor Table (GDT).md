2026-02-18 19:03

Tags: [[operating system development]] [[computer science]]

------------------------------------------------

### General:
The GDT contains *descriptors* of *memory segments* (see [[segmented memory allocation]]) . These contain the *base address*, the *limit* (size), the type (see [[memory segment types]]). It is initialized at boot, then stored in memory and writes the pointer to that memory address into the GDTR register.

### Segment registers:
These are specialised registers on the CPU that contain the so-called *segment selector*. It is a binary data structure specific to the x86-64 architecture and follows this Format:
![[Pasted image 20260218213938.png]]
This means:
- The first two bits (bits 0 and 1) determine the [[privilege level]] of the selector
- The third bit (bit 2) specifies the descriptor table. In the case that we use the GDT, we set this to 0.
- The remaining 13 bits (bits 3-15) contain the index in binary format.
For example, if the selector looks like this:
`0x10 = 0000 0000 0001 0000`
Then the first 2 bits are 0 -> privilige level 0; the third bit is 0 -> uses gdt; the last 13 as a **binary string** are `0000 0000 0001` - meaning they represent the index `1 x 2⁰ = 1`, corresponding to bit 8 (since if the selector is viewed as one binary string, the 1 would represent an 8 in decimal. This is called 8-[[bit alignment]])

In total, this selector takes up 16 bits = 2 bytes. It can be represented by a 2-digit hexadecimal number.

### Segment descriptor:







------------------------------------------------------
### References
https://chatgpt.com/c/6995fced-5ca0-832b-ab8f-6f9e24d84d9d
https://wiki.osdev.org/Segment_Selector
https://wiki.osdev.org/Global_Descriptor_Table
https://wiki.osdev.org/Segmentation
https://wiki.osdev.org/GDT_Tutorial
https://wiki.osdev.org/Global_Descriptor_Table
