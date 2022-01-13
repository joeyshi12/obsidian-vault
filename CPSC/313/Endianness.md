# Endianness

Endianness is the order of bytes for data in computers
- Big Endianness: LEFT HAS BIGGEST / Most significant digit on the lowest address
- Little Endianness (**Default**): LEFT HAS SMALLEST / Most significant digit on the highest address
- **Note**: Endianness does not change how items are placed in structs / arrays
	- `0x1000: 01 23 45 67 89 AB CD EF`
	- If `char a[2]` is read at location `0x1000`, we have `[0x01, 0x23]` for both little and big Endian

## Memory Address
Address order is given from top to bottom, left to right.
```
0x1000: 01 23 45 67 89 AB CD EF
0x1008: 03 69 BE 25 8C F1 47 AD
```
E.g., `0x23` is at a lower address than `0x69` which is at a lower address than `0x25`