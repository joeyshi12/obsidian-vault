# Chapter 11.1: The Ramsey number of a graph
For which $n\in\mathbb{N}$ is it possible to assign colours red and blue (not properly)
to $E(K_n)$, such that no $K_3$ subgraph has all red edges or all blue edges?

## Interpretation
$n$ people at the party.
Colour edges:
- Red if they know eachother
- Blue otherwise

Can we have a party that avoids a trio of all friends and avoids a trio of all strangers?

## Another interpretation
$G: $V(G) = V(K_n)$ and $E(G) = \{\text{red edges}\}$.
Can we find $G$, such that $K_3\not\subseteq G$ and $K_3\not\subseteq\overline{G}$.?

Call a colouring "good" of it has no monochromatic $K_3$
and "bad" otherwise.

$R(3, 3)$ is the min value of $n$, such that no good colouring exists.

Claim: there is no good colouring of $K_6$
ie, any red-blue colouring of $E(K_6)$ has a monochromatic triangle.
Then, $R(3,3)\leq 6$, so $R(3,3) = 6$.

## Proof
Any vertex of $K_6$ has 5 neighbours, so there are at least 3 edges incident to $v$
that were given the same colour (WLOG say blue)
Let $x, y, z\in{N(v)}$, such that $vx, vy, vz$ are all blue.
If $xy$ is blue, $vxyv$ is blue $K_3$.
If $xz$ or $yz$ is blue, $K_3$.
If none of $\{xy, yz, xz\}$ are blue, then all red, red $K_3$.

Given graphs $F_1,\dots, F_k$, each of which has $\geq 1$ edge,
$r(F_1,\dots, F_k$) is the smallest integer $n$,
such that any (not necessarily proper) colouring 
of $E(K_n)$ using $\leq k$ colours
has a copy of $F_i$ whose edges are all coloured for some $i$.
$R(i_1, i_2,\dots, i_k) = r(K_{i_1},\dots, K_{i_k})$.

## Example R(3, 4) = 9
That is, $n = 9$ is the smallest integer, such that any
red-blue colouring of $K_n$ has a $K_3$ subgraph whose edges are all red,
or a $K_4$ subgraph whose edges are all blue.

## Proof
$C_8$ has a good colouring, so $R(3, 4)> 8$.
Blue subgraph: $C_8^2$, red subgraph: $\overline{C_8^2}$.
Consider a red-blue colouring of $E(K_9)$.
Suppose a vertex $v$ has 4 red edges.
If any edge whose endpoints are red neighbours of $v$ is red,
they make red $K_3$.
If none of those edges are red, blue $K_4$.

If a vertex has 4 red edges, colouring is bad.
Suppose a vertex $v$ has 6 blue edges 