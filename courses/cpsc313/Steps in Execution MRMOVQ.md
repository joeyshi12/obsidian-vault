# Steps in Execution MRMOVQ
- **Fetch**
	- Get address of instruction from PC
	- Put instruction inside instruction register
    - Compute the next instruction address given no jumps `valP = PC + length(instruction)`
- **Decode**
    - Get `valC = offset`, `valB = R[rB]`, `valA = R[rA]`
- **Execute**
	- Use ALU to compute `valE = valB + valC` which is the address of the value being set into `%rax`
- **Memory**
	- Fetch the value from memory: `valM = M8[valE]`
- **Writeback**
	- Write back to the destination register `R[rA] <- valM`

| implemenation                        | allowed variables in each stage      |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20220117142737.png]] | ![[Pasted image 20220124142101.png]] |

