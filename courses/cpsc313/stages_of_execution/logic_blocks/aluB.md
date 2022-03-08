```C
uint64_t aluB(y86_icode_t icode, uint64_t valB) {
    switch (icode) {
        case I_MRMOVQ:
        case I_RMMOVQ:
        case I_OPQ:
        case I_PUSHQ:
        case I_POPQ:
        case I_CALL:
        case I_RET:
            return valB;
        default:
            return 0;
    }
}
```