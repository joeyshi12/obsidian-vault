---
course: "cpsc313"
title: "Memory Hierarchy & Strided Access"
---

## Memory Hierarchy
Things closer to the CPU implies
- Faster
- Smaller Size
- Smaller Cache Lines
- More Expensive

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
