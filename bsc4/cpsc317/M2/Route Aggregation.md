---
course: CPSC317
title: Route Aggregation
tags: IP
module: 3
date: 2022-10-12
---

Route aggregation/supernetting reduces the size of a routing table
and the number of advertisements by using summarization.

```
200.23.20.0/22
200.23.16.0/22
200.23.64.0/20

20 = 0b000101|00
16 = 0b000100|00

200.23.20.0/22} = 200.23.16.0/21
200.23.16.0/22}

Routing table
-------------
200.23.16.0/21
200.23.64.0/20
```