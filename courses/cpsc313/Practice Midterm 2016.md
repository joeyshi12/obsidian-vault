1a)
F gets register numbers and D gets their values. D depends on F to get the register number.

1b)
E does math and M reads and writes to memory. M depends on execute to compute memory addresses

1c)
D sets dstE and dstM and W writes values into these registers. W depends on D to set these register numbers.

2a) $t(i, r, c) = ic / r$
2b)

3a) (1, 3), (3, 4), (4, 5)
3b) ebx, ebx, eax
3c) 2, 3, 3
```C
[1] pop %eax            // pop stack top into %eax  
[2] irmovl $1, %ebx     // %ebx = 1  
nop
nop
[3] addl %eax, %ebx     // %ebx = %ebx + %eax  
nop
nop
nop
[4] mrmovl (%ebx), %eax // %eax = M[%ebx]  
nop
nop
nop
[5] push %eax           // push %eax onto the stack
```

4a)
a)
- e_valE -> d_valB
- e_valE -> d_valB
- m_valM -> d_valA
b) 0, 0, 1

4b)
Forwarding to E instead of D requires us to forward from the end of the memory stage to the start of the execute stage. We should not do this because we would need to wait for M to finish reading from main memory before starting the execute stage which would be costly.

4c)
We can not avoid stalling since we get valM from the end of the memory stage at the earliest and we need would need to forward this to d_valA. 1 stall

5a)
(b) is better because loops will have 2 incorrect predictions at worst in this case and (a) may have $(\text{number of iterations}) - 1$ incorrect predictions at worst

5b)
Conditional jump instructions could be executed without causing any bubbles or squashing.
However, we need 


6a)
Yes
No

7a)