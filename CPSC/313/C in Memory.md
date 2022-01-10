# C in Memory

## Alignment rule
A struct must be aligned by its largest variable type size, so each variable size must be padded so that its size is a multiple of the largest type size

```C
struct myStruct {
	char a;    // 1 + 3 bytes
	int32_t i; // 4 bytes
	char b;    // 1 + 3 bytes
}
```
