```C
// Fetch
icode:ifun = M1[PC]
rA:rB = M1[PC+1]
valP = PC + 1

// Decode
valA = R[rsp]
valB = R[rsp]

// Execute
valE = valB + 8

// Memory
valM = M8[valA]

// Writeback
R[rsp] = valE

// PC Update
PC = valM
```
