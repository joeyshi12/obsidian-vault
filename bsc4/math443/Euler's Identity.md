---
course: MATH443
title: Euler's Identity
tags:
date: [[2023-03-15]]
---

## Theorem
If $G$ is a connected, plane graph of order $n$ and size $m$,
and its plane drawing has $r$ regions, then
$$n - m + r = 2$$
In particular, all plane drawings of a planar graph have same \# of regions.

![[Euler's Identity 2023-03-15 15.04.46.excalidraw]]

## Proof
Let $G$ be a connected, planar graph with $n$ vertices,
$m$ edges. Let $r$ be the number of regions of a plane drawing of $G$.
We will proceed by induction of $m$.

**Base Case**: $m = n - 1$. Since $G$ is also connected, $G$ is a tree.
$G$ has no cycles, so by observation, $r = 1$, so
$n - m + r = n - (n - 1) + 1 = 2$.

**Induction Step**:  Suppose $m\geq n$ and theorem holds for all $n$ vertex planar graphs on $< m$ edges.
Since $\|G\|\geq |G|$ and $G$ is connected, $G$ has at least 1 cycle, so $G$ has an edge $e$ that is not a bridge.
That is $G - e$ is connected. In $G$, $e$ is on the boundary of exactly 2 regions (by observation)

![[Euler's Identity 2023-03-15 15.18.18.excalidraw]]

In $G-e$, those 2 regions combine into 1, so $G - e$ has $r - 1$ regions.
By the inductive hypothesis,
$$\begin{align*}
|G - e| - \|G - e\| + (r - 1) &= 2 \\
|G| - (\|G\| - 1) + r - 1 &= 2 \\
n - (m - 1) + (r - 1) &= 2 \\
n - m + r &= 2
\end{align*}$$