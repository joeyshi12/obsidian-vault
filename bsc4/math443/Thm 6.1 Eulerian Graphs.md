## Theorem 6.1
A nontrivial connected graph is Eulerian iff every vertex has even degree.

## Proof
Let $G$ be a nontrivial connected graph whose vertices all have even degree.
Let $C$ be a maximal length trail in $G$.

**Claim**: $C$ is closed. If not, it has an endpoint $u$ with odd degree in $C$.
Since $u$ has even degree in $G$, there exists an edge $uv\in{E(G)}\setminus{E(C)}$.
But, $C + uv$ is a longer trail (CONTRADICTION).
So, trail of maximum length must be closed.

If $E(C) = E(G)$$, then we're done.
BWOC, suppose not. Since $G$ is connected, there exists some $xy\in{G}$, where $x\in{V(C)}$.
Consider $G - E(C)$. Since $C$ is a circuit, all vertices have an even degree in $C$,
so they have even degree in $G - E(C)$.
Consider a maximal length trail $D$ starting at $xy\in{G - E(C)}$.
As before, $D$ is closed.
Splice $D$ into $G$ at $x$: $xCxDxCx$.
This is longer than $C$ (CONTRADICTION).

![[6.1 Eulerian Graphs 2023-03-03 15.13.38.excalidraw]]