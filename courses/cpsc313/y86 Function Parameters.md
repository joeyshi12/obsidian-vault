## Function Parameters
- Function parameters are passed in registers in the order of: `rdi, rsi, rdx, rcx, r8, r9`
	- Additional arguments are pushed onto the stack in reverse order (e.g. push arg 8 then arg 7, etc...)
	- If a param is too big for a register, then pass onto the stack

## Register Usage
- Caller saved registers
	- Callee is allowed to scribble over these, so caller must save the contents if they want to use the values
    - `rdi, rsi, rdx, rcx, r8, r9, r10, r11`
- Callee saved registers
	- Callee must restore the original values before returning
	- `rbx, rbp, r12, r13, r14`

## Example
- Consider the function `int myfunc(int p1, structa p2, int p3, structb p4);`
- myfunc has local variables `a, b, c` which are all quadwords

```c
int myfunc(int p1, structa p2, int p3, structb p4) {
	...
	quadword a = ...;
	quadword b = ...;
	quadword c = ...;
	...
}

p2 is 16 bytes
p4 is 24 bytes

NOTE: Address increases from left to right



Without stack pointer:
			 8  8  8  8               16  24
Stack: [...][c][b][a][return address][p2][p4][...] 



With stack pointer:
			 8  8  8  8          8               16  24
Stack: [...][c][b][a][saved rbp][return address][p2][p4][...] 

%rbp = &(saved rbp)
8(%rbp) = &(return address)
16(%rbp) = &p2
32(%rbp) = &p4
```

![[Pasted image 20220118224115.png]]