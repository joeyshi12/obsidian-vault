# Bit Operations

## Bit Shifting
- `<<` = left shift operator
- `>>` = right shift operator

```C
char c = 0b00000001;
c <<= 6; // 0b01000000
c >>= 7; // 0b00000000
```

## Logical Operations
- AND (&)
- XOR (^)

```
0xEEEE & 0x1111

1110 1110 1110 1110
0001 0001 0001 0001

0000 0000 0000 0000

0x0000
```

```
0xEEEE ^ 0x1111

1110 1110 1110 1110
0001 0001 0001 0001

1111 1111 1111 1111

0xFFFF
```

```
0x9393 & 0xA0A0

1001 0011 1001 0011
1010 0000 1010 0000

1000 0000 1000 0000

0x8080
```