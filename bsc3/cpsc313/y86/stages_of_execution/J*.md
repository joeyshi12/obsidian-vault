```C
// Fetch
icode:ifun = M1[PC]
valC = M8[PC + 1]
valP = PC + 9

// Decode
NULL

// Execute
Cnd = Cond(CC, ifun)

// Memory
NULL

// Writeback
NULL

// PC Update
PC = Cnd ? valC : valP
```