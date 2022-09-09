```C
int memCntrl(y86_icode_t icode){
    if (icode == I_RMMOVQ || icode == I_PUSHQ || icode == I_CALL) return 4;
    if (icode == I_MRMOVQ ||  icode == I_RET || icode == I_POPQ) return 2;
    return 0;
}
```