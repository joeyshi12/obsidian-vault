## Move register to register: RRMOVQ
- 2-byte instruction
- `RRMOVQ %r8, %r9`
	- In memory, this is `20 89`, where
	- `0x20` is the op code,
	- `0x89` represents register 8 to 9
![[y86 Instructions 1.png]]

## Move immediate value to register: IRMOVQ
- 10-byte instruction
- `IRMOVQ 0xCAFE, %r9`
	- In memory, `30 F9 FE CA 00 00 00 00 00 00`, where
	- `0x30` is the op-code,
	- `0xF9` represents register 9,
	- the last 8 bytes represent the value going into register 9
![[y86 Instructions 2.png]]

## Move value in memory to register: MRMOVQ
- 10-byte instruction
- Think of memory `M_8` as an array of 8-byte values
- `MRMOVQ 4(%rsp), %r9`
	- In memory, `50 94 04 00 00 00 00 00 00 00`, where
	- `0x50` is the op-code,
	- `0x94` represents `%rA` and `%rB` used in the figure
	- the last 8 bytes represent the offset `D`
![[y86 Instructions 3.png]]

## Move register to value in memory: RMMOVQ
- 10-byte instruction
- `RMMOVQ %r9, 4(%rsp)`, where
	-  In memory, `40 94 04 00 00 00 00 00 00 00`, where
	- `0x40` is the op-code,
	- the last 8 bytes represent the offset `D`
![[y86 Instructions 4.png]]