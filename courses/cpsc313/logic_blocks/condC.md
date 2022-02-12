```C
int cond(y86_condition_t ifun, int OF, int SF, int ZF)
{
    if (ifun == C_LE) {
        return ZF || SF;
    } else if (ifun == C_L) {
        return SF;
    } else if (ifun == C_E) {
        return ZF;
    } else if (ifun == C_NE) {
        return !ZF;
    } else if (ifun == C_GE) {
        return !SF;
    } else if (ifun == C_G){
        return !SF && !ZF;
    } else {
        return 1;
    }
}
```