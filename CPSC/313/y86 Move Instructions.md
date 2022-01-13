## Move register to register: RRMOVQ
- 2-byte instruction
- Op-code: 20
- `rrmovq %r8, %r9`
	- In memory, this is `20 89`, where
	- `0x89` represents register 8 to 9

![[y86 Instructions 1.png]]

## Move immediate value to register: IRMOVQ
- 10-byte instruction
- Op-code: 30
- `irmovq 0xCAFE, %r9`
	- In memory, `30 F9 FE CA 00 00 00 00 00 00`, where
	- `0xF9` represents register 9,
	- the last 8 bytes represent the value going into register 9

![[y86 Instructions 2.png]]

## Move value in memory to register: MRMOVQ
- 10-byte instruction
- Op-code: 50
- Think of memory `M_8` as an array of 8-byte values
- `mrmovq 4(%rsp), %r9`
	- In memory, `50 94 04 00 00 00 00 00 00 00`, where
	- `0x94` represents `%rA` and `%rB` used in the figure
	- the last 8 bytes represent the offset `D`

![[y86 Instructions 3.png]]

## Move register to value in memory: RMMOVQ
- 10-byte instruction
- Op-code: 40
- `rmmovq %r9, 4(%rsp)`, where
	-  In memory, `40 94 04 00 00 00 00 00 00 00`, where
	- the last 8 bytes represent the offset `D`