# Steps in Execution (mrmovq example)
- Fetch
	- Get address of instruction from PC
	- Place instruction inside instruction register
	- ValP = PC + length(instruction) is the next instruction address (assuming no jumps)
- Decode
	- Parse instruction:
		- Get ValC = offset, ValB = R[rB], rA
		- ValB = R[rB] is the register value in rB
- Execute
	- Use ALU to compute ValE = ValB + ValC which is the address of the value being set into %rax
- Memory
	- Fetch the value from memory using the ValE address: ValM = M[ValE]
- Writeback
	- Write back to the destination register R[rA] = ValM

![[Pasted image 20220117142737.png]]

## Allowed variables in each stage
![[Pasted image 20220124142101.png]]