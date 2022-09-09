## Overview
- [[y86 Registers]]
- [[y86 Instructions]]
- [[Y86_instruction_set_cheat_sheet.pdf]]
- [[y86 Diagrams]]


## Condition codes
- A collection of bits set by arithmetic and logical instructions used for [[y86 Jump Instructions ]]
- Zero-flag: The last ALU operation produced a 0
- Sign-flag: The last ALU operation produced a negative number (produced a number with 1 in the high order bit)
- Overflow-flag: The last ALU operation produced an overflow


##  Status Register
- Indicates normal operation or an error condition
	1. AOK Normal Operation
	2. HLT Halt Instruction encountered
	3. ADR Bad address encountered
	4. INS Invalid instruction encountered


## Program Counter (PC)
- Indicates the address of the next instruction to execute
- For non-jumping instructions: nextPC = valP = PC + sizeof(currInst)


## Main Memory (DMEM)
- Byte-addressable storage array
- Words stored in [[Endianness | Little Endian]] order

![[y86 Codes.png]]