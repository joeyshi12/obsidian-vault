```C
uint64_t data(uint64_t valA, uint64_t valP, y86_icode_t icode)
{
    if (icode == I_RRMVXX || icode == I_RMMOVQ || icode == I_PUSHQ) {
        return valA;
    } else if (icode == I_CALL) {
        return valP;
    } else {
        return 0xBAAAAAAD;
    }
}
```