A **perfect matching** in a graph $G$ is a spanning 1-regular
subgraph of $G$.

# Theorem 8.14
For each positive integer $k$, the edge set of $K_{2k}$ vertices
can be partitioned into $2k-1$ perfect matchings.

## Proof
Set $V(K_{2k}) = \{v_0,\dots, v_{2k-1}\}$.
Arrange $\{v_1,\dots, v_{2k-1}$ on plane as regular polygon.
Put, $v_0$ in the center.
Matching $M_i$ ($1\leq i\leq 2k-1$)
consists of $v_0v_1$ and all edges perpendicular to $v_0v_i$

![[Thm 8.14 Perfect Matching 2023-03-29 15.26.51.excalidraw]]

That is $M_i = \{v_0v_1\}\cup \{v_{i-j}v_{i+1} : i\leq j \leq k-i\}$.

## Notes
1. $|M_i| = 1 + (k - 1) = k$, so each $M_i$  has $k = \frac{|K_{2k}|}{2}$ edges.
2. $\sum_{i=1}^{2k-1} |M_i| = (2k - 1)(k) = \frac{2k(2k-1)}{2} = \|K_{2k}\|$.
3. Every edge is in some matching. Consider $v_av_b$, $a\leq b$. If $a=0$, $v_av_b = v_0v_b\in{M_b}$. If $a\neq 0$, $v_a$ and $v_b$ are on polygon, so there is a direction along polygon where they have odd distance. Then, the vertex in middle of that path is $v_i$, and $v_av_b\in{M_i}$.

$\chi'(K_n) = n-1$ if $n$ is even (each perfect matching is a colour class. So,
$$\chi'(K_n) = \begin{cases}
n - 1 &\text{if } n \text{ even} \\
n &\text{if } n \text{ odd}
\end{cases}$$
