```C
uint64_t addr(uint64_t valB, uint64_t valE, y86_icode_t icode) {
    if (icode == I_POPQ || icode == I_RET) {
        return valB;
    } else if (icode == I_PUSHQ || icode == I_CALL || icode == I_MRMOVQ || icode == I_RMMOVQ) {
        return valE;
    } else {
        return 0xBAAAAAAD;
    }
}
```