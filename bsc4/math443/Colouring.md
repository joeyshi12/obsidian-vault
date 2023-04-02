---
course: MATH443
title: Colouring
tags: colouring
date: [[2023-03-22]]
---

Let $G$ be a graph.
A proper $k$-colouring of $G$ is a function $f: V(G)\to [k]$,
such that if $xy\in{E(G)}$, $f(x)\neq f(y)$.

The colour class of a colour $a$ is
$[a] = \{v\in{V(G)} : f(v) = a\} = f^{-1}(\{a\})$.

We think of edges as conflicts.
Colour classes partition $V(G)$ into conflict-free sets.

![[Colouring 2023-03-22 15.30.28.excalidraw]]

For example, if a graph $G$ has $V(G)$: classes that have a final exam,
$xy\in{E(G)}$ iff some student enrolled in both.
Ideally: if colours correspond to exam times, colouring proper.

$\chi(G)$ is the chromatic number of a graph $G$, defined as the smallest $k$,
such that a proper $k$-colouring of $G$ exists
if a proper $k$-colouring of $G$ exists, we say $G$ is $k$-colourable.

Observeration: $\chi(G)\leq |G|$ with equality if and only if $G$ is complete.
If $G$ is not complete, there exists distinct $x, y\in{V(G)}$, such that $xy\not\in{E(G)}$.
Assign $x,y$ same colour, every other vertex gets a unique colour.
That is, a proper ($|G| - 1$) colouring.

$\omega(G)$ is the clique number of $G$,
$\omega(G) = \max\{n : K_n\subseteq G\}$.

Observation: $\chi(G)\geq \omega(G)$.

Observation: $\chi(G)\leq \Delta(G) + 1$.
Why? Greedy colouring: colour vertices 1-by-1.
Use a colour not yet assigned to any vertex in $N(v)$ on $v$.
There is always such a colour.

Observation: $\chi(G)\geq \frac{|G|}{\alpha(G)}$.
Each colour assigned to vertices of an independent set.
$\alpha(G)$:  [[Independence Number]].
Each colour is used on $\leq \alpha(G)$ vertices.
So, it takes at least $\frac{|G|}{\alpha(G)}$ colours to properly colour $G$.

## Example
Image colouring a map of countries on plane/sphere, such that
contries sharing positive length borders have different colours.