# Theorem 10.13
Let $G$ be a graph of odd order, $n$ with $m$ edges.
If $m > \frac{(n-1)\Delta(G)}{2}$, then $\chi'(G) = \Delta(G) + 1$.

## Proof
Since $n$ is odd, each colour is used on at most $\lfloor n/2\rfloor = \frac{n-1}{2}$ edges.
So, $\Delta(G)$ colours can colour at most $\frac{n-1}{2}\Delta(G)$.
If $m > \frac{(n-1)\Delta(G)}{2}$, then $\chi'(G) > \Delta(G)$.
By Vizing's theorem, $\chi'(G) = \Delta(G) + 1$.