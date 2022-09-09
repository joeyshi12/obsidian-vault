- Cache hit = 4 cycles
- Cache miss = 16 cycles for read + writes
- Write to DRAM takes 8 cycles
- Data can be written to the cache and DRAM in parallel

**What write hit rate will make the average write time be the same for both write-through (write no-allocate) and write-back (write allocate) caches?**

```
writeHitRate = x

Write-back:
(1-x)(16) + x(4)

Write-through:
8

(1-x)(16) + x(4) = 8
16 - 8 = 12x
x = 8/12 = 2/3 = 0.67
```