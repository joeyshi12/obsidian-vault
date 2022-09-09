---
course: "cpsc313"
title: "Clock Page Replacement"
source: "P27"
---

## Motivation
- We can't use our cache eviction policies because the OS does not know the access pattern
- Accesses are handled by MMU/hardware, so we don't have time to update counts or most recently accessed

## Clock Algorithm (LRU Approximation)
1. Physical pages are arranged around a clock
2. Each time a page is accessed, the HW will set its use bit to 1
3. If we access a new page (e.g., 77), we move clockwise until we reach a page with use bit = 0 and evict that page
    1. Pages that we skip over have their use bit set back to 0

![[Pasted image 20220406041902.png|500]]