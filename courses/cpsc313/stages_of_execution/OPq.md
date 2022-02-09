```C
// Fetch
icode:ifun = M1[PC]
rA:rB = M1[PC]
valP = PC + 2

// Decode
valA = R[rA]
valB = R[rB]
dstE = rB

// Execute
valA = valB op valA
set CC

// Memory
NULL

// Writeback
R[dstE] = valE

// PC Update
PC = valP
```