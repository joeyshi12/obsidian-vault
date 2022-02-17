```C
int cond(y86_condition_t ifun, int OF, int SF, int ZF) {
    switch (ifun) {
        case C_LE:
            return ZF || SF;
        case C_L:
            return SF;
        case C_E:
            return ZF;
        case C_NE:
            return !ZF;
        case C_GE:
            return !SF;
        case C_G:
            return !SF && !ZF;
        default:
            return 1;
    }
}
```