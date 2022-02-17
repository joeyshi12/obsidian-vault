---
course: "cpsc313"
title: "Caching (reads)"
---

## Cache Line (block) size Tradeoffs
- Large cache lines can be good:
    - If your data exhibit good spatial locality
- Large cache lines can be bad:
    - If your data does not exhibit good spatial locality
    - Consider the 1KB cache line and imagine that we only use one byte out of every KB
    - We consume a lot of cache space and still take a miss on every byte

    
## Cache line (block) size Summary
- Cache line gets smaller as you get closer to the processor (like how cache size decreases as you get to the processor)
    - Hardware cache lines are always powers of two
- **The beginning of a cache line is a power of 2 **

## How do I decide where to place a cache line?
- Problem: We have large set of object we want to map to a much smaller set of locations
- General approach
    - Hashing
- Address
    - | Tag | Index (hash) into the cache | Offset in cache line |
- Offset
    - The number of bits in this part are a function of the cache line size
- Index
    - Determined by number of lines in the cache
    - e.g. cache holds 128 cache lines, then I need to index 128 entries (0-127); requires 7 bits
- Tag

## Evaluating a cache
- Cache hit rate:
    - number of cache hits / number of cache accesses
    - number of cache hits / (number of cache hits + number of cache misses)
- We want a high hit rate