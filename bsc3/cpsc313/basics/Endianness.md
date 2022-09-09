# Endianness
Endianness is the order of bytes for data in computers
- Big Endianness: most significant digit on lower address / biggest on left side
- Little Endianness: least significant digit on lower address / smallest on left side
- *Endianness does not change how items are placed in structs / arrays*
	- `0x1000: 01 23 45 67 89 AB CD EF`
	- If `char a[2]` is read at location `0x1000`, we have `[0x01, 0x23]` for both little and big Endian

**Example:**
Address order is given from top to bottom, left to right.
```
0x1000: 01 23 45 67 89 AB CD EF
0x1008: 03 69 BE 25 8C F1 47 AD
```
E.g., `0x23` is at a lower address than `0x69` which is at a lower address than `0x25`r