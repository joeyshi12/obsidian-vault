# Primitive Data Types

For this course, we use data types for 32-bit CPU
- char = 1 byte
- short = 2 bytes
- uint32_t = unsigned 4 byte integer
- int32_t = signed 4 byte integer

## Other data type sizes (implementation dependent)
- pointer = usually 4 or 8 bytes
- function = pointer = 4 or 8 bytes

## Signed vs unsigned
- Signed
	- Range:  $[-2^{n-1}, 2^{n-1}-1]$
	- **Two's complement**: flip all bits and add 1 to get the opposite signed number
- Unsigned range
	- Range:  $[0, 2^{n}-1]$