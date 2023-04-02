---
course: MATH443
title: Discharging
tags:
date: [[2023-03-20]]
---

## Observation

Let $G$ be a planar graph,
and assign to each vertex $v$ in $G$ initial charge $\mu(v) = 6 - d(v)$.
Then,
$$\begin{align*}
\sum_{v\in{V(G)}} \mu(v) &= \sum_{v\in{V(G)}} (6 - d(v)) \\
&= 6|G| - 2\|G\| \\
&\geq 6\|G\| - 2(3|G| - 6) \\
&= 6|G| - 6|G| + 12 \\
&= 12
\end{align*}$$
If $G$ is a triangulation, then equality holds.