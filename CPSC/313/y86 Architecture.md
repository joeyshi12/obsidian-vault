## Registers
- High speed memory for data manipulation
- y86 has 15 registers
- y86 registers are 64-bit

## Condition codes
- A collection of bits set by arithmetic and logical instructions used for [[y86 Control Flow ]]
- Zero-flag: The last ALU operation produced a 0
- Sign-flag: The last ALU operation produced a negative number (produced a number with 1 in the high order bit)
- Overflow-flag: The last ALU operation produced an overflow

##  Status Register
- Indicates normal operation or an error condition
	1. AOK Normal Operation
	2. HLT Halt Instruction encountered
	3. ADR Bad address encountered
	4. INS Invalid instruction encountered

## Program Counter
- Indicates the address of the next instruction to execute

## Memory (DMEM)
- "Main memory" / "How much DRAM"
- Byte-addressable storage array
- Words stored in [[Endianness | Little Endian]] order

![[y86 Architecture.png]]