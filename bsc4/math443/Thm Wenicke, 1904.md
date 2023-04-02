# Theorem (Wenicke, 1904)

If a triangulation has minimum degree 5,
then it has an edge $xy$, such that $d(x) = 5$ and $d(y)\in\{5, 6\}$.

## Proof

Let $G$ be a triangulation
For all $v\in{V(G)}$, assign an initial charge $\mu(v) = 6 - d(v)$.
Note $\sum_{v\in{V(G)}} \mu(v) = 12 > 0$.
Discharge according to the following rule:
- Any vertex of degree 5 donates charge 1/5 to each neighbour.

Since charge is neither created nor destroyed,
$$
\sum_{v\in{V(G)}} \mu^*(v) = \sum_{v\in{V(G)}} \mu(v) > 0.
$$
So, there exists $w\in{V(G)}$, such that $\mu^*(w) > 0$.
Note: for any $v\in{V(G)}$, $\mu^*(v)\leq (6 - d(v)) + \frac{1}{5}d(v)$.
So, $0 < \mu^*(w)\leq 6 - \frac{4}{3}d(w)$
$\frac{4}{5}d(w) < 6$
$d(w) < 7.5$, so $d(w)\in\{5, 6, 7\}$.

**Case 1**: $d(w) = 5$.
$\mu(w) = 6 - 5 = 1$
$w$ donated $1/5$ to all its neighbours.
$0 < \mu^* = (1) - (1/5)(1) + (1/5)(\text{\# deg-5 neighbours})$,
so $w$ has a neighbour of degree 5, so theorem holds.

**Case 2**: $d(w) = 6$.
$\mu(w) = 0$, so $w$ got a donation, so it has a neighbour of degree 5,
so theorem holds.

**Case 3**: $d(w) = 7$.
$0 < \mu^*(w) = (6 - 7) + (1/5)(\text{\# deg-5 neighbours})$,
so $w$ has at least $6$ degree 5 neighbours.
From last time, because $G$ is a triangulation,
$N(v)$ is spanned by a cycle, $C_7$,
so at least 6 of these neighbours have degree 5, so
there exists 2 adjacent degree 5 neighbours => theorem holds.