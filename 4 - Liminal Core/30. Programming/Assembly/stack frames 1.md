2025-03-08 14:04

Tags: [[Assembly]]

------------------------------------------------
##### Definition:
part of the general stack of an assembly script designated to a routine

contains the local variables, current registers, return address and function parameters

##### Keywords:

**base pointer (ebp)** = pointer that saves the address of the bottom of the stack, used in reference to address values within the stack (doesnt require you to write e.g. esp + 12312 for complex stacks)

**stack pointer (esp)** = pointer that contains the current top of the stack, therefore the limit of possible entries. Increased using 
*sub esp, 16*
if more space is needed

**local variables** = variables solely used in the current routine / function

**return address** = the position in the memory (allocated to the program) where it should continue to execute after the routine is finished

##### Usage // Process:

Step 1: The old base pointer is saved to the stack, indicating the end of the last stack frame

*push ebp*

Step 2: The top of the stack (which defines the size / space for values / the memory allocated to the stack) is copied to the base pointer of the stack frame (base pointer now holds address of the "bottom" of the frame)

*mov ebp, esp*

Step 3: Space for local variables is added onto the stack by increasing the stack pointer (esp) so that the limit is higher than before

*sub esp, X      ;(e.g. 16, used in bytes)*

Step 4: Rest of the function

Step 5: esp is set to the base pointer, deallocating space for local variables

*mov esp, ebp*

Step 6: the old base pointer is restored by deleting the current base pointer from the stack (it´s currently the newest value since the variables have been deleted in previous step)

*pop ebp*

##### Recap by Copilot:

- **Function Call:**
    
    - Caller saves the current state.
        
    - Adjusts the stack pointer (SP) to make space for the new stack frame.
        
- **Function Prologue:**
    
    - Callee saves the old base pointer (BP) onto the stack.
        
    - Sets the new base pointer (BP) to the current stack pointer (SP).
        
    - Allocates space for local variables.
        
- **Function Execution:**
    
    - Local variables and function parameters are accessed via the base pointer (BP).
        
- **Function Epilogue:**
    
    - Stack pointer (SP) is adjusted to remove local variable space.
        
    - Restores the old base pointer (BP).
        
- **Function Return:**
    
    - Caller restores saved registers and adjusts the stack pointer (SP).


------------------------------------------------------
### References

Copilot: https://copilot.microsoft.com/chats/8jxY72zvAeggds4FYLNHK
Stack Overflow: https://stackoverflow.com/questions/3699283/what-is-stack-frame-in-assembly
Stack: [[stack]]
ESP: [[4 - Liminal Core/30. Programming/Assembly/ESP]] 
EBP: [[4 - Liminal Core/30. Programming/Assembly/EBP]] 
Registries: [[registry]] 