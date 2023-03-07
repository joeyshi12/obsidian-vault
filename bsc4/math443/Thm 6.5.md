## Theorem 6.5
If $G$ is Hamiltonian graph, then for every nonempty set $S\subseteq V(G)$. $k(G - S) \leq |S|$.
**Note**: $k(G)$ is the number of components in $G$

## Observe
If a graph has a cut vertex, it's not Hamiltonian.
If $v$ is a cut vertex of $G$, $k(G - \{v\}) \geq 2 > |\{v\}|$.

## Proof
Let $G$ be a Hamiltonian graph.
Let $S\subseteq V(G)$, $S \neq \emptyset$.
Let $G_1, G_2, \dots, G_{k(G - S)}$ be the components of $G - S$.
Let $C$ be a Hamiltonian cycle of $G$.
Impose a direction on $C$.
For $i\in{[k(G - S)]}$,
let $x_i$ be the last vertex of $G_i$ on $C$ and let $s_i$ be the vertex directly following $x_i$ on $C$.

![[Thm 6.5 2023-03-03 15.36.47.excalidraw]]

The vertex $s_i$:
- can't be in $G_i$ ($x_i$ was the last vertex of $G_i$ in $C$)
- can't be in $G_j$ for any $G_j \neq i$ (then $G_i$, $G_j$ are in the same component of $G - S$)
- So, $s_i\in S$

Since $C$ is a cycle (not circuit), $i\neq j \Rightarrow s_i \neq s_j$.
So, $|S| \geq |\{s_1,\dots, s_{k(G - S)}\}| = k(G - S)$.