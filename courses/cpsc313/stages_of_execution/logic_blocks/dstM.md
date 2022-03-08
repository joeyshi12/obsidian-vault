```C
y86_register_t dstM(y86_register_t rA, y86_icode_t icode){
    if (icode == I_MRMOVQ || icode == I_POPQ) return R_RAX;
    return 0xF;
}
```