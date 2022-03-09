---
course: "cpsc313"
title: "Tutorial 5"
---

## Fundamentals
1. A cache is a smaller intermediate memory store that is placed closer to local. Ex. a fridge
2. Accessing main memory is very slow, having an intermediate storage is faster
3. Yes
4. IDK WTF
5. Cache lines should be a power of 2

## Average Access Times
1. $0.5(1) + 0.5(5) = 3 \text{cycles}$
2. $0.6(1) + 0.4(5) = 2.6 \text{cycles}$
3. $\frac{3}{2.6} = 1.15$

## Computing Hit/Miss Rates
1. $62/64$ miss when reading first 2 bytes (compulsory), but rest of cache line is available
2. $15/16$
3. $7/8$ miss f
4. $62/64$  compulsory miss + miss from reading in-between cache lines

## Cache Associativity
Fully associative => no index bits
Direct map => One-way 

3. If arrays A1, A2 are accessed with same index in address, then we will be constantly overwriting the cache lines when accesses their elements. Having a 2-way set associative cache will help us