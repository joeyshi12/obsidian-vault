---
course: CPSC317
title: Hamming Codes
topic: Error Detection
tags: Error Detection, Link Layer Services
module: 3
lecture: 10
date: [[2022-10-7]]
---

## Parity Check
- Sum the bits of 101101 and check parity
- The sender sends 101101(0); 0 is appended.
- The receiver receives 1001010
    - ParityCheckError: sum of payload bits is odd, but parity check if even

## Hamming Codes: 2D Parity Checking
```
Example: 10101 01011 10111

1 0 1 0 1 | rowsum = 1
0 1 0 1 1 | rowsum = 1
1 0 1 1 1 | rowsum = 0
----------
0 1 0 0 1            0
colsums

Send: 10101(1) 01011(1) 10111(0) (010010)
```

The Receiver can
- Identify the flipped bit if 1 bit was flipped
- If there are 2 errors along the diagonal, then an error is detected, but the error bits can be in 2 of 4 possible positions
- If there are an even number of flipped bits on each row and column, then they cannot identify the error
