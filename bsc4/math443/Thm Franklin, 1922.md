# Theorem (Franklin, 1922)

In every planar graph with minimum degree 5,
some vertex of degree 5 has 2 neighbours of degree at most 6.

| $d(v)$ | $\mu(v)$  | undesirable                                       |
| ------ | --------- | ------------------------------------------------- |
| 5      | 6 - 1 = 1 | Donates charge 1/4 to all neighbours of 7 or more |
| 6      | 6 - 6 = 0 | Don't do anything                                 |

## Proof

WLOG, let $G$ be a triangulation, $\delta(G)\geq 5$.
Assign initial charge $\mu(v) = 6 - d(v)$ to each $v\in{V(G)}$.
Discharging rule: a vertex of degree 5 donates charge of 1/4 to all neighbours of degree  7 or more.
$$\sum \mu^*(v) = \sum \mu(v) = 12 > 0$$
So, there exists $w\in{V(G)}$, such that $\mu^*(w) > 0$.
If $d(w) = 5$, by choice of rule, $v$ has at least 2 neighbours of degree 5 or 6 and the theorem holds.

If $d(w) = 6$, then $\mu(w) = 0$, $w$ does not donate or receive charge,
so $\mu^*(w) = 0$ (CONTRADICTION).

If $d(w) \geq 8$,
$$\begin{align*}
\mu^*(w)&= (6 - d(w)) + \frac{1}{4}(\text{\# neighbours of degree 5}) \\
&\leq 6 - d(w) + \frac{1}{4}d(w) \\
&= 6 - \frac{3}{4}d(w) \\
&\leq 6 - \frac{3}{4}\delta(G) = 0 \text{ CONTRADICTION}
\end{align*}$$

If $d(w) = 7$,
$$\begin{align*}
0 &< \mu*(w) = (6 - 7) + \frac{1}{4}(\text{\# degree 5 neighbours}) \\
1 &< \frac{1}{4}(\text{\# degree 5 neighbours})
\end{align*}$$
So, $w$ has at least 5 degree 5 neighbours. Recall $G\subseteq G[N(w)]$.
Then , $N(v)$ has a vertex of degree 5 with 2 neighbours of degree 5.