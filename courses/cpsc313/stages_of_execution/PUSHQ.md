```C
// Fetch
icode:ifun = M1[PC]
rA:rB = M1[PC + 1]
valP = PC + 2

// Decode
valA = R[rA]
valB = R[rsp]

// Execute
valE = R[rsp] - 8

// Memory
M8[valE] = valA

// Writeback
R[rsp] = valE

// PC Update
PC = valP
```