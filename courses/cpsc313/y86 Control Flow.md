## Jump Instructions

![[Jump Instructions.png|600]]

| Instruction | Op-Code | Condition |   Check   |
|:-----------:|:-------:|:---------:|:---------:|
|     JMP     |   70    |   None    |     1     |
|     JLE     |   71    |   <= 0    | ZF \| SF  |
|     JL      |   72    |    < 0    |    SF     |
|     JE      |   73    |   == 0    |    ZF     |
|     JNE     |   74    |   != 0    |    !ZF    |
|     JGE     |   75    |   >= 0    |    !SF    |
|     JG      |   76    |    > 0    | !ZF & !SF |

## Conditional register to register moves
- CMOVLE
- CMOVL
- CMOVE
- CMOVNE
- CMOVGE
- CMOVG