# Y86 Stack
- Stack grows from upper address to lower address
- Program and data (heap and static) grows from lower to upper address

## PUSHQ
- 2-byte instruction
- Op-code = `0xA0`
- Subtracts 8 bytes from stack pointer, moves chosen register value into stack pointer address in main memory
![[Pasted image 20220116201625.png|600]]

# Pop
- 2-byte instruction
- Op-code = 0xB0
- Sets value in stack pointer address from main memory into chosen register, adds 8 bytes to stack pointer
![[Pasted image 20220116211448.png|600]]

# Function Call and Return
- **Call**
    - Push next instruction address into stack, set the PC to new destination (start of function)
    - Example: `.pos 0x10b0: call foo`
    	- Call is a 9-byte instruction, so the next instruction is at `0x10b9`
    	- Push `0x10b9` into the stack
```C
// pushq PC
R[%rsp] <- R[%rsp] - 8
M8[R[%rsp]] <- PC
// Update PC
PC <- Dest
```
- **Return**
```C
// popq PC
PC <- M8[R[%rsp]]
R[%rsp] <- R[%rsp] + 8
```

![[Pasted image 20220116213349.png|600]]