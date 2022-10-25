---
course: CPSC317
title: Recursive Search
topic: DNS Search
tags: DNS
module: 4
lecture: 2
date: [[2022-10-14]]
---

- Pro: intermediate results can get cached
- Caching exploits locality
    - NS for .cs.ubc.ca will benefit from caching remote.students.cs.ubc.ca
    - .ca (Canada) and root (North America) will likely not benefit from caching remote.students.cs.ubc.ca

![[Recursive Request 2022-10-14 09.19.58.excalidraw|800]]