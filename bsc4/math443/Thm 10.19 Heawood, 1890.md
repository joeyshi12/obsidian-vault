# Theorem 10.19 (Heawood, 1890 using ideas of Kempe)
Every planar graph is 5-colourable

## Proof
By  induction on $|G|$, where $G$ is a planar graph.

**Base case**: $|G| \leq 5$, then $\chi(G) \leq 5$.

**Induction step**: Suppose $|G|\geq 6$ and all planar graphs on fewer than $|G|$ vertices are 5-colourable.
If $\delta(G)\leq 4$, let $v\in{V(G)}$ of min degree.
$G-v$ planar, so by induction hypothesis, there exists a proper 5-colouring.
$|N(v)|\leq 4$, so there is a colour not used on $N(v)$.
Assigning $v$ that colour give a proper 5-colouring of $G$.

So, assume $\delta(G) > 4$.
Then, $\delta(G) = 5$.
Let $v\in{V(G)}$, such that $d(v) = 5$.
$G - v$ is planar, so there exists a proper 5-colouring.
If a 5-colouring of $G-v$ exists, such that $N(v)$ has at most 4 colours,
then there is a colour not in $N(v)$ to assign to $v$.
This makes a proper 5-colouring of $v$.

We claim such a colouring of $G-v$ exists.
Suppose BWOC in every proper 5-colouring of $G-v$,
$N(v)$ receives precisely 5 colours.

Fix a 5-colouring of $G-v$.
FOr distinct $i,j\in{[5]}$,
we define $G_{i,j}$ to be the subgraph of $G-v$ induced by colour classes $i$ and $j$
(filter for vertices of class $i$ and $j$).
Note: in any component of $G_{i, j}$, if we swap colours $i, j$ in every vertex of that component,
the result is a proper 5-colouring of $G-v$.

Fix a plane drawing of $G$ and label $N(v) = \{v_1,\dots, v_5\}$ in order (say counter-clockwise)
in the drawing. By assumption, they are assigned exactly 5 colours.
WLOG, say $v_i$ has colour $j$.

![[Thm 10.19 Heawood, 1890 2023-03-27 15.19.17.excalidraw]]

Let $i, j$ be distinct elements of $[5]$.
If $v_i, v_j$ are in different component s of $G_{i, j}$,
then we can toggle $i, j$ in the component of $v_j$.
The result is a proper 5-colouring of $G-v$, such that
2 vertices in $N(v)$ have have colour $i$  => CONTRADICTION.
So, $v_i, v_j$ are in the same component of $G_{i, j}$.
$v_1, v_3$ are in the same componet of $G_{1, 3}$.
So, there is a $v_1-v_3$ path in $G_{1, 3}$.
Since it is in $G_{1, 3}$, all vertices of that path have colour 1 or 3.

![[Thm 10.19 Heawood, 1890 2023-03-27 15.26.54.excalidraw]]

The path plus $v_1\times v_3$ is a cycle in $G$.
$v_2$ and $v_4$ are on opposite "sides" of the cycles.
(the cycle alone defines 2 regions; $v_2, v_4$ in different regions.

Now consider $G_{2, 4}$.
By assumption, $v_2, v_4$ are in the same component of $G_{2, 4}$.
So, there exists $v_2, v_4$ path whose vertices are all coloured 2 and 4.
Since $v_2, v_4$ are on different sides of the $v_1-v_3$ cycle $C$.
Either:
- The $v_2-v_4$ path has an edge crossing on edge $C$ (CONTRADICTS PLANE DRAWING)
- Or, it shares a vertex with $C$ (CONTRADICTS vertices of $C$ coloured 1 and 3; vertices of $P$ coloured 2 and 4; no vertex has 2 colours)