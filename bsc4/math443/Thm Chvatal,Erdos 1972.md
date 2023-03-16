## Theorem (Chvatal, Erdos 1972)
Let $G$ be a graph with $\geq 3$ vertices.
If there exists an integer $s$, such that $G$ is $s$-connected and
$\alpha(G)\leq s$ ([[Independence Number]]), then $G$ is Hamiltonian.

## Proof
Let $G$ be a graph on $\geq 3$ vertices.
Let $s$ be an integer, such that $\kappa(G)\geq s$, $\alpha(G)\leq s$.
- If $s = 1$, then since $\alpha(G)\leq 1$, then $G$ is complete, so $G$ is Hamiltonian.
- Now suppose $s \geq 2$

Since $\kappa(G)\geq 2$, $G$ has a cycle.
Let $C$ be a cycle of maximum length in $G$.
If $C$ is spanning, then we are done.
BWOC, assume there exists $x\in{V(G)\setminus V(C)}$.
Since $G$ is $s$-connected, by previous work,
there exists paths $P_1,\dots, P_s$ and vertices $x_1,\dots, x_s$
such that $P_i$ is an $x-x_i$ path, such that $V(P_i)\cap V(C) = \{x_i\}$ for all $i\in [s]$
and if $i\neq j$, then $V(P_i)\cap V(P_j) = \{x\}$.

Impose a direction on $C$.
Label vertex after $x_i$ as $y_i$ for all $i\in [s]$.
(maybe $y_i = x_{i+1}$, maybe not)

Case 1: there exists $y_i$, such that $xy_i\in{E(G)}$
$x_iP_ixy_iCx_i$ is a longer cycle than $C$ => CONTRADICTION.

Case 2: $xy_i\not\in{E(G)}$ for all $y_i$
$S = \{x, y_1, \dots, y_s\}$ is a set of size $s + 1$.
Since $\alpha(G) \leq s$, there exists an edge between 2 vertices in $S$.
Since $xy_i\not\in{E(G)}$, $y_iy_j\in{E(G)}$ for some $y_i, y_j$.
$x_iCy_jy_iCx_jP_jxP_ix_i$ is a longer cycle than $C$ => CONTRADICTION.
