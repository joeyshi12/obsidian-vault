# Endianness

Endianness is the order of bytes for data in computers
- Big Endianness: Most significant digit on the lowest address
- Little Endianness (**Default**): Most significant digit on the highest address

## Memory Address
Address order is given from top to bottom, left to right.
```
0x1000: 01 23 45 67 89 AB CD EF
0x1008: 03 69 BE 25 8C F1 47 AD
```
E.g., `0x23` is at a lower address than `0x69` which is at a lower address than `0x25`