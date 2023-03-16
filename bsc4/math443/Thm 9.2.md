## Theorem 9.2
If $G$ is a planar graph of order $n\geq 3$ and size $m$, then $m\leq 3n - 6$.

## Proof
First, consider a connected graph $G$ with $n$ vertices, $m$ edges.
Suppose a plane drawing of $G$ has faces $F_1,\dots, F_r$.
Let $l(F_i)$ be the number of edges on the boundary of $F_i$.

Since $G$ is connected, $\|G\|\geq 2$.
If $\|G\| = 2$, then $G = P_3$.
Then, $m = 2$, so $3n - 6 = 3$, so theorem holds.

Now suppose $\|G\|\geq 3$. By observation, $l(F_i)$ for all $i\in{[r]}$.
So, $\sum_{i=1}^{r} l(F_i)\geq 3r$
Every edge (by observation) is on the boundary of precisely 1 or
precisely 2 faces, so $\sum l(F_i)$ counts every edge once or twice.
So, $3r\leq \sum l(F_i) \leq 2m$.

By [[Euler's Identity]],
$$\begin{align*}
2 &= n - m + r \\
6 &= 3n - 3m + 3r \\
  &\leq 3n - 3m + 2m \\
  &= 3n - m \\
m &\leq 3n - 6
\end{align*}$$

## Corollary 9.4
$K_5$ is non-planar.

## Proof
$n = 5$, so $3n - 6 = 9$.
$m = \binom{5}{2} = 10 \not\leq 9$.

