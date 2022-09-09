# Fermat Factorization
Suppose $n$ is the product of 2 positive integers $n = pq$. 
- $n = pq = \left(\frac{p + q}{2}\right)^2 - \left(\frac{p - q}{2}\right)^2$, so $n$ can be written as the difference of 2 squares
- $\frac{p + q}{2} \geq \sqrt{n}$

```python
from math import sqrt, ceil

def fermat_factorize(n):
    # REQUIRES: n = pq
    a = ceil(sqrt(n))
    b2 = a**2 - n
    b = isqrt(b2)
    while b < 0: # check b2 is not square
        a += 1
        b2 = a**2 - n
        b = isqrt(b2)
    return (a + b, a - b)

def isqrt(n):
    # Binary search for integer root
    # time complexity: O(log(n))
    i = 0
    j = n // 2
    while i <= j:
        p = (i + j) // 2
        p2 = p * p
        if p2 == n:
            return p
        if p2 < n:
            i = p + 1
        else:
            j = p - 1  
    return -1
```

**example.** $n = 5959$

$\lceil \sqrt{n} \rceil = 78$
$\min\{x^2 : x^2 > n, x\in\mathbb{Z}\} = 80^2$

$5959 = 80^2 - 21^2 = 101\cdot 59$