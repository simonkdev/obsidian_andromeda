2025-08-19 12:26

Tags: [[computer science]]

------------------------------------------------

##### Overview:
A computer's memory is split into memory cells, which store one bit (0 or 1) each. 8 of these cells form a set, which has the size of one byte (8 bits = 1 byte).
These sets can be addressed using a memory address, also called a pointer. They are written in [[hexadecimal notation]] and point to one of these sets. 


##### Content of one set:
Inside the hardware, the value is saved as a binary, which can hold any pattern of 8 binary digits, meaning:

**Numerical Range** (integers):
- Unsigned (only positive): 0 to 255 (2⁸ = 256)
- Signed (positive and negative)
**Characters**:
- any [[ASCII]] or extended ASCII character (in numerical form, e.g. 65 = 'A')
- In [[UTF-8]], one character may take up to 4 bytes

##### Real-World:
What exactly the byte represents depends on the context. It could be either of these (e.g.):
- small integer (e.g. 200)
- single letter (e.g. 65 = 'A')
- color channel value in an image (0-255)
- part of a larger integer (e.g. 1/4 of a 32-bit int)
- flag field (each bit is true or false)
The context is determined by the [[CPU]]. Every [[CPU architectures]] has an instruction set (ISA), which represent a set of instructions the CPU can execute. 
The instruction being executed then determines what the address is interpreted as. 

When a program wants to run an instruction, it allocates a position in the memory space for this program. The kernel determines which program gets CPU time, therefore which program's queue is next to get a frame of execution time. The CPU registries have an Instruction pointer stored, which points to the next instruction in a program's memory. As soon as a program receives CPU time, the CPU then looks at the instruction located at the pointer and executes it.

 [[paged memory allocation]]

------------------------------------------------------
### References