# Theorem (Borodin, 1989)

If $G$ is a triangulation with $\delta(G)\geq 3$,
then $G$ has
- an edge $xy$, such that $d(x) + d(y)\leq 11$ (edge of weight less than 11)
- *OR a 4-cycle with 2 vertices of degree 3, that have a common neighbour on the cycle of degree 9 or 10.*

## Proof

Let $G$ be a triangulation,
$\mu(v) = 6 - d(v)$.
Suppose for any $xy\in{E(G)}$, $d(x) + d(y)\geq 12$.
If $d(v)\in\{3, 4, 5\}$, then $v$ donates all its charge (equally)
to its neighbours. That is, it donates $\frac{6 - d(v)}{d(v)}$ to each neighbour.
Note: only vertices of degree less than 5 donate charges.
Their neighbours have degrees greater than 7.
So, only degree 7 and up vertices receive charge.

Assign initial charge $\mu(v) = 6 - d(v)$ for all $v\in{V(G)}$.
- If $d(v)\in\{3, 4, 5, 6\}$, then $\mu^*(0)$ is the final charge.
    - Note: in a triangulation, $N(v)$ spanned by a cycle $C$ since no donor vertices adjacent to each other, $v$ has at most $\lfloor d(v)/2 \rfloor$ donor neighbours.
- If $d(v)\geq 11$,
    - $\mu^*(v)\leq \lfloor 6 - d(v)\rfloor + \lfloor d(v)/2\rfloor \leq 6 - \lceil d(v)/2\rceil \leq 6 - \lceil 11/2\rceil = 0$
- If $d(v) = 7$, then it can only receive donations from deg 6 vertices, so $\mu^*(v)\leq (-1) + (1/5)\lfloor d(v)/2\rfloor\leq (-1) + 3/5 < 0$
- If $d(v) = 8$, then it can only receive donations from deg 4 or 5 neighbours, so $\mu^*(v)\leq (-2) + (1/2)(8/2) = 0$.

So, if $\mu^*(v) > 0$< then $d(v)\in\{9, 10\}$.
Such a vertex exists because $\sum \mu^*(v) = \sum \mu(v) = 12 > 0$.
Now assume $d(v)\in\{9, 10\}$.

**Note**: say $N(v)$ is spanned by cycle $C$.
If 2 deg 3 vertices are at distance 2 along $C$ (\*), then $G$ has $C_4$,
that has 2 nonadjacent deg 3 vertices with common neighbour of deg 9 or 10, and theorem holds.

![[Thm Borodin, 1989 2023-03-22 15.16.08.excalidraw]]

If $d(v) = 9$,  and if $\mu^*(v) > 0$: let $a$ be the number of deg 3 neighbours of $v$. Then, $v$ has at most $4 - a$ other donor neighbours, so: $0 < \mu^*(v)\leq (-3) + (1)(a) + (1/2)(4 - a)$ implies $a\geq 3$.

If $a = 3$:
$0 < \mu^*(v) = (-3) + 3 + (1/2)(\text{\# other donor neighbours})$
So, $v$ has 4 donor neighbours, 3 of them deg 3.

If $a\geq 3$, then $a = $, so $v$ has 4 ddonor neighbours all deg 3.

![[Thm Borodin, 1989 2023-03-22 15.19.10.excalidraw]]

If $d(v) = 10$ and $\mu^*(v) > 0$: let $a$ be the number of degree 3 neighbours of $v$.
$v$ has at most 5 donor neighbours, so: $0 < \mu^*(v)\leq (-4) + (1)(a) + (1/2)(5 - a)$,
which implies $a\geq 4$, so $v$ has configuration (\*) from the **note**,
so theorem holds.