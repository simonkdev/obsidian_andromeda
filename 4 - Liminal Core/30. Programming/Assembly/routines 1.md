2025-03-08 13:49

Tags: [[Assembly]] 

------------------------------------------------

##### Overview: 
a routine is the name for a function in assembly, often executed by a caller in start

##### Example:
_start:
    call add_numbers   ; Call the add_numbers routine     <-- caller in start

    ; Exit the program
    mov eax, 60        ; System call for exit (60)
    xor edi, edi       ; Status 0 (success)
    syscall            ; Invoke the system call

add_numbers:                              <-- "routine" called add_numbers
    ; Load the values into registers
    mov al, [num1]     ; Move the value of num1 into the AL register
    add al, [num2]     ; Add the value of num2 to the AL register

    ; Store the result
    mov [result], al   ; Move the value of AL (result) into the result variable

    ret                ; Return from the routine



------------------------------------------------------
### References
Copilot: https://copilot.microsoft.com/chats/yVnouFsQGrRGKgw4N8aD8
Caller and Callee: [[caller and callee]] 