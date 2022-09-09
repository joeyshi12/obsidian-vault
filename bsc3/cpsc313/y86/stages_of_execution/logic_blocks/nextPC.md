```C
uint64_t nextPc(uint64_t valC, uint64_t valM, uint64_t valP, int cond, y86_icode_t icode){
    if ((cond != 0 && icode == I_JXX) || icode == I_CALL) {
        return valC;
    } else if (icode == I_RET) {
        return valM;
    } else {
        return valP;
    }
}
```