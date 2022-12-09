---
course: CPSC304
title: Benefit of Materializing a View
topic: Views
tags:
module: 8
date: [[2022-12-01]]
---

## HRU Algorithm
- Greedy algorithm for answering queries in the cheapest way
- Does not guarantee an optimal solution

## Notation for Calculating Benefit
- $S :=$ Set of views selected for materialization.
- $b\subseteq a$ means $b$ is a descendant of $a$.
- $C(v) :=$ Cost of view $v$, which is approximated by the size of the view.

```python
# initialize benefit(view) = 0
B[v, S] = 0
for w in v.descendants():
    u = <least cost ascendant of u in S>
    B[v, S] += max(C(u) - C(v), 0)
```

## Clicker Question

![[Pasted image 20221201160901.png|600]]
- Answer: $2(5.8M) = 11.6M$

## In-class Exercise

Assuming 'a' is already materialized, what are the best 3 other views that we should materialize?
Begin by   picking the “best” view to materialize. 

| View | 1st choice    | 2nd choice      | 3rd choice     |
| ---- | ------------- | --------------- | -------------- |
| b(1) | ->50(6) = 300 |                 |                |
| c    | 25(6) = 150   | 25(2) = 50      | 25(2) = 50     |
| d    | 80(3) = 240   | 30(3) = 90      | 30             |
| e    | 70(4) = 280   | 20(4) = 80      | 20(2) = 40     |
| f(3) | 60(3) = 180   | 60 + 10(2) = 80 | ->60 + 10 = 70 |
| g(2) | 99(2) = 198   | ->49(2) = 98    |                |
| h    | 90(2) = 180   | 40(2) = 80      | 40             |
| i    | 99            | 49              | 0              |

![[Pasted image 20221201163214.png|400]]