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
A descriptor also has a specific layout, described by this table:
![[Pasted image 20260220224427.png]]


### Flags:
The flag part of the segment descriptor follows this architecture:
![[Pasted image 20260220223917.png]]
**G**: Granularity, the value that the limit value is scaled by (therefore determining its unit). If it is 0, the limit will not be scaled and be the exact number of bits available. If it is 1, it will be scaled by  4KiB, meaning it shows the limit in the number of pages.

**D/B**: Size flag. If clear (**0**), the descriptor defines a 16-bit protected mode segment. If set (**1**) it defines a 32-bit protected mode segment. A GDT can have both 16-bit and 32-bit selectors at once.

**L:** Long-mode code flag. If set (**1**), the descriptor defines a 64-bit code segment. When set, **DB** should always be clear. For any other type of segment (other code types or any data segment), it should be clear (**0**).


### Access Byte:
This part of the segment descriptor follows this architecture:
![[Pasted image 20260220223953.png]]
**P**: Present bit, 1 for any valid segment

**DPL**: Contains the [[privilege level]], 0 for highest privilege (kernel), 3 for lowest (users)

**S**: Descriptor type: clear (0) means it is a system segment (e.g. [[Task State Segment (TSS)]]), 1 means it is a code or data segment

**E**: Executable bit, if clear (0) it defines a data segment, if it is 1 it defines a code segment and it is executable

**DC**: Direction bit:
- For data selectors: Direction bit. If clear (0) the segment grows up. If set (**1**) the segment [grows down](https://wiki.osdev.org/Expand_Down "Expand Down"), ie. the **Offset** has to be greater than the Limit.
- For code selectors: Conforming bit.
    - If clear (0) code in this segment can only be executed from the ring set in **DPL**.
    - If set (1) code in this segment can be executed from an equal or lower privilege level. For example, code in ring 3 can far-jump to _conforming_ code in a ring 2 segment. The **DPL** field represent the highest privilege level that is allowed to execute the segment. For example, code in ring 0 cannot far-jump to a conforming code segment where **DPL** is 2, while code in ring 2 and 3 can. Note that the privilege level remains the same, ie. a far-jump from ring 3 to a segment with a **DPL** of 2 remains in ring 3 after the jump.

**RW:** Readable bit/Writable bit.
    - For code segments: Readable bit. If clear (**0**), read access for this segment is not allowed. If set (**1**) read access is allowed. Write access is never allowed for code segments.
    - For data segments: Writeable bit. If clear (**0**), write access for this segment is not allowed. If set (**1**) write access is allowed. Read access is always allowed for data segments.

**A:** Accessed bit. The CPU will set it when the segment is accessed unless set to **1** in advance. This means that in case the GDT descriptor is stored in read only pages and this bit is set to **0**, the CPU trying to set this bit will trigger a page fault. Best left set to **1** unless otherwise needed.







------------------------------------------------------
### References
https://chatgpt.com/c/6995fced-5ca0-832b-ab8f-6f9e24d84d9d
https://wiki.osdev.org/Segment_Selector
https://wiki.osdev.org/Global_Descriptor_Table
https://wiki.osdev.org/Segmentation
https://wiki.osdev.org/GDT_Tutorial
https://wiki.osdev.org/Global_Descriptor_Table

