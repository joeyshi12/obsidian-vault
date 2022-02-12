```C
y86_register_t srcB(y86_register_t rB, y86_icode_t icode){
    // return R_RAX;
    if (icode == I_RMMOVQ || icode == I_MRMOVQ || icode == I_OPQ) {
        return rB;
    } else if (icode == I_PUSHQ || icode == I_POPQ || icode == I_CALL || icode == I_RET) {
        return R_RSP;
    } else {
        return R_NONE;
    }
}
```