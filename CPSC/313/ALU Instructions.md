## Arithmetic and Logical Instructions
- 2-byte instruction
- Op-codes
	- ADDQ: 60
	- SUBQ: 61
	- ANDQ: 62
	- XORQ: 63

![[ALU Operations.png]]

## Bonus Instructions
- Op-codes
	- MULQ: 64
	- DIVQ: 65
	- MODQ: 66

## Condition Codes
- Recall that [[y86 Architecture#Condition codes| condition codes]] (ZSO) are set after an ALU operation
- Condition codes are used in [[y86 Control Flow]]