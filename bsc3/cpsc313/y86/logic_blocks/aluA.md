```C
uint64_t aluA(y86_icode_t icode, uint64_t valC, uint64_t valA){
    switch (icode) {
        case I_RRMVXX:
        case I_OPQ:
            return valA;
        case I_IRMOVQ:
        case I_MRMOVQ:
        case I_RMMOVQ:
            return valC;
        case I_PUSHQ:
        case I_CALL:
            return 8;
        case I_POPQ:
        case I_RET:
            return -8
        default:
            return 0xBAAAAAD;
    }
}
```