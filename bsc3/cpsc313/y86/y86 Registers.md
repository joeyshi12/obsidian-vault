## Registers
- High speed memory for data manipulation
- 15 registers. 8-bytes
    - `%rcx, %rdx, %rbx, %rsp, %rbp, %rsi, %rdi, %r8-14`
- [[y86 Function Parameters]]
    - Order: `rdi, rsi, rdx, rcx, r8, r9`
    - If value is greater than 8 bytes or registers are all used, then push param onto the stack in *reverse order* (arg8, arg7, arg3....)
