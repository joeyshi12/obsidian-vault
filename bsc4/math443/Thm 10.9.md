# Theorem 10.9
$\chi(G) \leq 1 + \max\{\delta(H) : H \leq G\}$

## Proof
Let $G$ be an $n$ vertex graph.
Set $v_n$ to be a vertex of minimum degree in $G$.
For $i = n-1, n-2,\dots, 1$:
    set $v_i$ to be a vertex of min degree in $G - \{v_{i+1},\dots, v_n\}$

Colour vertices in order $v_1,\dots, v_n$
assign to $v_i$ a colour not used in $G[v_1,\dots, v_{i-1}]$.
Such a colour exists because: \# already coloured neighbours of $v_i$ is
$$\begin{align*}
d_{G[v_1,\dots, v_{i-1}]}(v_i) &= \delta(G[v_1,\dots, v_{i-1}]) \\
&\leq \max\{\delta(H) : H \leq G\} \\
&< 1 + \max\{\delta(H) : H\leq G\}.
\end{align*}$$
