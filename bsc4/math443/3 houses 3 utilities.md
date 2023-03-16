[[Chapter 9 Planarity#3 houses, 3 utility problems.]]

## Observation
From [[Thm 9.2]], if $m = 3n - 6$, then $\sum_{i=1}^{r} l(F_i) = 3r$.
So, every face has $3$ edges (it is a triangle).
A planar graph in which every face has boundary $C_3$ is a **trangulation**.

Any triangulation is "maximally planar".
That is, if we add any edge, it is no longer planar ($m > 3n - 6$).

Any planar  graph is a spanning subgraph of a triangulation.

![[Thm 9.2 2023-03-15 15.39.49.excalidraw]]

## Proof

Let $G$ be a planar, bipartite graph with $n$ vertices, $m$ edges, $r$ regions.
We follow the proof of [[Thm 9.2]] until $\sum_{i=1}^{r}\geq 4r$.
In the case $G$ is not a tree, every face has a cycle on its boundary.
Every cycle has $\geq 4$ edges in $G$ because it is bipartite.
Following the algebra through as in Thm 9.2: $m\leq 2n - 4$.

So, in a bipartite planar graph $G$, $|G|\geq 4$, $\|G\|\leq 2|G| - 4$.
For $K_{3,3}$, $n = 6, 2n - 4 = 8, m = 9\not\leq 8$. So, $K_{3,3}$ is not planar.