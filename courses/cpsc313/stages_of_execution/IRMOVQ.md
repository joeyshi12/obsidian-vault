```C
// Fetch
icode:ifun = M1[PC]  
rA:rB = M1[PC + 1]  
valC = M8[PC + 2]  
valP = PC + 10

// Decode
dstE = rB

// Execute
valE = valC + 0

// Memory
NULL

// Writeback
R[dstE] = valE

// PC Update
PC = valP
```