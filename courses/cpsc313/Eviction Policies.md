## Belady's Algorithm
- This is the best eviction algorithm
- Always evict the item that we use farthest in the future
    - Assume we have 2 slows in our cache
    - Assume fully associative
    - We access cache blocks in the following order
        - A, A, C, A, C, B, B, B, A, A, B, C

```
Miss A
Hit  A
Miss C
Hit  A
Hit  C
Miss B (Kick A) // This is still considered compulsory since B has not been accessed yet
Hit  B
Hit  B
Miss A
Hit  A
Hit  B
Miss C

Compulsory misses: 3
Capacity misses: 1
Hits: 8
Hit rate: 8/12
```

## LRU: Least Recently Used
- Evict the item that was used farthest in the past

## LFU: Least Frequently Used
- Keep track of how many times each item is used and replace the one with the smallest frequency count

```
BEAD
```

