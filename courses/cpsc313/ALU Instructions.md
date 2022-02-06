## Arithmetic and Logical Instructions
- 2-byte instruction
- Op-codes
	- ADDQ: 60
	- SUBQ: 61
	- ANDQ: 62
	- XORQ: 63
	- MULQ: 64 (+)
	- DIVQ: 65 (+)
	- MODQ: 66 (+)

![[ALU Operations.png|700]]


## Condition Codes
- Recall that [[y86 Architecture#Condition codes| condition codes]] (ZSO) are set after an ALU operation
- Condition codes are used in [[y86 Control Flow]]