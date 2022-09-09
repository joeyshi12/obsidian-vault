```C
uint64_t increment_pc(uint64_t pc, y86_icode_t icode){
    if (icode == I_HALT || icode == I_NOP || icode == I_RET) {
        return pc + 1;
    } else if (icode == I_RRMVXX || icode == I_OPQ || icode == I_PUSHQ || icode == I_POPQ) {
        return pc + 2;
    } else if (icode == I_JXX || icode == I_CALL) {
        return pc + 9;
    } else if (icode == I_IRMOVQ || icode == I_RMMOVQ || icode == I_MRMOVQ) {
        return pc + 10;
    } else {
        return 0;
    }
}
```