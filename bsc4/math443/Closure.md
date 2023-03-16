## Definition
The **closure** $C(G)$ of a graph $G$
is the graph obtained from $G$ by iteratively adding edges between nonadjacent vertices
whose degrees sum to at least $|G|$, until no such pair remains.

![[Closure 2023-03-06 15.34.50.excalidraw]]

## Proposition
The closure of a graph is unique

## Proof
Let $G_1$ and $G_2$ be closures of $G$.
Say $G_1 = G\cup\{f_1,\dots, f_k\}$ and $G_2 = G\cup\{e_1,\dots, e_s\}$.
If $G_1\neq G_2$, then there exists $f_i\not\in{E(G_2)}$.
Choose $i$ minimum. Then, $\{f_1,\dots, f_{i-1}\}\subseteq E(G_2)$, so $G\cup \{f_1,\dots, f_{i-1}\}\subseteq G_2$
$f_i$ was "addable" in $G\cup\{f_1,\dots f_{i-1}\}$.
It's endpoints do not have lower degree in $G_2$, so
$f_i$ addable to $G_2$ (CONTRADICTION).
$G_2 = C(G)$, so $f_i\in{E(G_2})$.
