---
title: "Cyclic Redundancy Check"
topics: ["Error Detection"]
module: 3
lecture: 10
---

## Polynomial Division

$1010 \to 1x^3 + 0x^2 + 1x + 0 = x^3 + x$
$1011011101 \mod x^3 + x = q$
$\deg(q) \leq 2 \to \text{3 bits}$

```
1010  110101101(000)
      1010
      ----
      011101101000
       1010
       ----
       01001101000
        1010
        ----
        0011101000
          1010
          ----
          01001000
           1010
           ----
           0011000
             1010
             ----
             01100
              1010
              ----
              0110
    
Remainder = 110
Send: 110101101(110)

This work is done by cascading XORs using the XOR gate
The 1010 divisor is standard
```