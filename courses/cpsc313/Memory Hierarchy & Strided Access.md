---
course: "cpsc313"
title: "Memory Hierarchy & Strided Access"
---

```C
Suppose the cache line is 8 bytes

Access 1 byte at a time:
Stride 1: M H H H H H H H // hit rate = 7/8

Access 2
Stride 2: M.  H.  H.  H.  // hit rate = 3/4

Access 3
Stride 4: M.      H.      // hit rate = 1/2
```

## Code: Spatial Locality
- Stride size is the distance in memory
```C
[20][4][48][20][4][48]
    |   72     |

// stride = 72
```

## Strided Access in Real Life
| T0   | T1   | ... | T99  | T0   | T1   | ... | T99  | T0   | T1   | ... | T99  |
| ---- | ---- | --- | ---- | ---- | ---- | --- | ---- | ---- | ---- | --- | ---- |
| 9:00 | 9:00 |     | 9:00 | 9:05 | 9:05 |     | 9:05 | 9:10 | 9:10 |     | 9:10 | 

See: `Mar4/ecology.c`
