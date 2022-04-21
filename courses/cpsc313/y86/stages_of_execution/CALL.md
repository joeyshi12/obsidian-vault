```C
// Fetch
icode:ifun = M1[PC]  
valC = M8[PC + 1]  
valP = PC + 9  

// Decode
valB = R[rsp]

// Execute
valE = valB - 8

// Memory
M8[valE] = valP

// Writeback
R[rsp] = valE

// PC Update
PC = valC
```