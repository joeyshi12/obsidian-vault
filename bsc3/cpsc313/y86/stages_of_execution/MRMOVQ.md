```C
// Fetch
icode:ifun = M1[PC]
rA:rB = M1[PC + 1]
valC = M8[PC + 2]
valP = PC + 10

// Decode
valB = R[rB]
dstM = rA

// Execute
valE = valB + valC

// Memory
valM = M8[valE]

// Writeback
R[dstM] = valM

// PC Update
PC = valP
```