```C
// Fetch
code:ifun = M1[PC]  
rA:rB = M1[PC+1]  
valP = PC +2

// Decode
valA = R[rA]
dstE = rB

// Execute
valE = valA + 0  
Cnd = Cond(CC, ifun)

// Memory
NULL

// Writeback
if (Cnd) R[dstE] = valE

// PC Update
PC = valP
```