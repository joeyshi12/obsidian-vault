# Y86 Stack
- Stack grows from large / top address to small / bottom address
- Program and data (heap and static) grow "up"

## PUSHQ
- 2-byte instruction
- Op-code = 0xA0
- Subtracts 8 bytes from stack pointer, moves chosen register value into stack pointer address in main memory
![[Pasted image 20220116201625.png]]

# Pop
- 2-byte instruction
- Op-code = 0xB0
- Sets value in stack pointer address from main memory into chosen register, adds 8 bytes to stack pointer
![[Pasted image 20220116211448.png]]

# Function Call and Return
![[Pasted image 20220116213349.png]]

# Function Call
- Push next instruction address into stack, set the PC to new destination (start of function)
- Example: `.pos 0x10b0: call foo`
	- Call is a 9-byte instruction, so the next instruction is at `0x10b9`
	- Push `0x10b9` into the stack

![[Pasted image 20220116214723.png]]

# Function Return
- Pop PC from stack
![[Pasted image 20220116215150.png]]