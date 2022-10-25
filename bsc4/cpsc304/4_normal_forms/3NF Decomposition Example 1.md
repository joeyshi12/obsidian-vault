---
course: CPSC304
title: 3NF Decomposition Example 1
tags: 3NF, Normal Form Decomposition
module: 4
date: [[2022-10-13]]
---

```
R(ABCDEFG)

AB -> C
C -> D
EG -> F
F -> E

AB+ = ABCD
C+ = CD
EG+ = EGF
F+ = EF

F is a minimal cover

(DEFG(AB)C)
R1(ABC)
R2(ABDEFG)

(ABD(EG)F)
R3(EGF)
R3(ABDEG)

(EG(AB)D)
R4(ABD)
R5(ABEG)
```