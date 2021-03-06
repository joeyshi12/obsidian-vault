Write-Through: write to both cache and memory
Write-Back: write to cache and write to memory only when we evict the element from the cache

Example: 32B direct-map cache, 4B blocks, 8-bit address
- Offset = 2bit

```C
char* a = 0x234;
i = a[1]; // &a[1] = 0x235

// 0x23[5], 5 => 01 01
a[1] = 11
```

| V   | D   | Tag | Block    |     |
| --- | --- | --- | -------- | --- |
| 0   | 0   |     |          | 00  |
| 1   | 0   | 23  | 0,11,3,4 | 01  |
| 0   | 0   |     |          | 10  |
| 0   | 0   |     |          | 11  |

| Hit/Miss | .                               |
| -------- | ------------------------------- |
| Hit      | W.T. (D.S.)                     |
|          | W.B. (C)                        |
| Miss     | W.T. (D.S.)                     |
|          | W.B. clean (D.S.)               | 
|          | W.B. evict dirty line (D.S.)\*2 |

*Note: this means if we have a writethrough cache, it does not matter if the writes are hits or misses. They always take as long as to write to data source because cache write and data source write happens in parallel*

## Write Miss
- No Write Allocate
    - Data-source updated, cache not affected
- Write Allocate
    - Move from data source to cache

A write miss occurs when the dirty bit is set and we have a tag mismatch  `valid && dirty && (A >> tag_offset) != tag`