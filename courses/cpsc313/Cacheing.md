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
- [[Cache Bit Calculations]]

## Evaluating a cache
- Cache hit rate:
    - number of cache hits / number of cache accesses
    - number of cache hits / (number of cache hits + number of cache misses)
- We want a high hit rate
