---
course: "cpsc313"
title: "Multicore Caching: MSI Protocol"
source: "P17.1"
---

## Problem
- If all caches are write-back, the first core might access data that is dirty in the second core's cache
1. Suppose we have a *write allocate* policy and the left core is writing to a value  `X = 0x1234` for the first time.
2. The `X` value will be pushed into the L2 cache and then into  the L1 cache and value will be over-written in the L1 cache (`X = 0xCAFE`)
3. If the right core is accessing `X` for the first time, then it will receive `X = 0x1234` in the L2 cache

OR

If a cache from processor 1 reads `X`, processor 2 reads `X` and processor 1 writes to `X` in memory,
the value in processor 2 would have *stale data*

![[Pasted image 20220306205906.png|700]]

## Cache Coherence
- It is the hardware's job to avoid such inconsistencies
- Snoopy caches
    - All cores monitor the bus connecting the cores and invalidates other copies in cores of data item when a core is writing
    - Metadata: { M (dirty bit), S (cache line is shared), I (cache line is invalid/no valid data)  }
    - Read, write, remote read, remote write, evict can update this metadata

![[Pasted image 20220306212247.png|500]]