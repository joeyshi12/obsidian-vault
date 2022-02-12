```C
y86_register_t srcA(int cond, y86_icode_t icode, y86_register_t rB){  
    switch (icode) {  
        case I_RRMVXX:
            if (cond == 0) return R_NONE;
            // Fall-through
        case I_OPQ:  
        case I_IRMOVQ:
            return rB; 
        case I_PUSHQ:  
        case I_POPQ:  
        case I_CALL:  
        case I_RET:  
            return R_RSP;  
        default:  
            return R_NONE;  
    }  
}
```