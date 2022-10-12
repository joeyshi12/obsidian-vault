---
course: "cpsc304"
title: "3NF Decomposition"
topic: "Normal Form Decomposition"
module: 4
lecture: 10
tags: ["Normal Forms", "3NF", "Normal Form Decomposition"]
date: [[2022-10-11]]
---

## Method 1: Lossless Join method
1. Find a minimal cover $F'$ of $F$
2. For each FD $X \to b$ in $F'$, add relation $Xb$ to the decomposition for $R$
3. If there are no relations in the decomposition that contain all of the attributes of a key, add in a relation that contains all the attributes of a key. This preserves lossless joins.

```
R(CSJDPQV)
SD -> P
JP -> C
J -> S

SD -> P violates 3NF in R
(CJQV(SD)P)
R1(SDP)
R2(CJQVSD)

J -> S violates BCNF in R2
(CQVD(J)S)
R3(JS)
R4(CQVDJ)

JD -> C violates BCNF in R4
(QVD(J)S)
R5(JS)
R6(QVDJ)

No more violations
Are all FDs preserved? No, add R7(CJP)
```