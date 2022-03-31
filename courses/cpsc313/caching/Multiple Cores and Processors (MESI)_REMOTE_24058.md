---
course: "cpsc313"
title: "Multiple Cores and Processors"
---

Suppose we are sending an invalidation message to other cores, but
no other cache has the same cache line
*this is the most common case*

**This is expensive!**

## MESI
```
M: Modified
E: Exclusive - The data does not live in any other cache
S: Shared
I: Invalid
```

![[Pasted image 20220307143729.png|700]]

![[Pasted image 20220319223156.png]]

