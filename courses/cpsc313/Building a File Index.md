---
course: "cpsc313"
title: "Building a File Index"
week: 10
date: "3/16"
---

Main memory is treated as a cache for persistent data
This is a shared cache

![[Pasted image 20220316140903.png|600]]

![[Pasted image 20220316141136.png|700]]

Question: 4kB block, 4B block, 1GB max file size. How many blocks required for smallest file?
Answer: 
```
# blocks in file = 2^(30)/2^(12) = 2^(18)
size of index = 2^(18)*2^(2) = 2^(20) = 1MB
```
