```C
// Fetch
icode:ifun = M1[PC]
rA:rB = M1[PC + 1]
valC = M8[PC + 2]
valP = PC + 10

// Decode
valA = R[rA]
valB = R[rB]

// Execute
valE = valB + valC

// Memory
M8[valE] = valA

// Writeback
None

// PC Update
PC = valP
```