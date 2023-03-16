## Theorem 6.11 (Posa)
Let $G$ be a graph of order $n\geq 3$.
If: for every integer $j$ with $1\leq j < n/2$,
the number of vertices of $G$ with degree at most $j$ is less than $j$, then $G$ is Hamiltonian.

## Proof (contrapositive)
Let $G'$ be a graph of order $n\geq 3$ that is not Hamiltonian.
Let $G = C(G')$ [[Closure]].
We showed $C(G')$ is Hamiltonian iff $G'$ is Hamiltonian [[Thm 6.9]],
so $G$ is non-Hamiltonian.

Since $|G| \geq 3$ and is non-Hamiltonian, $G$ is not complete.
- If $G$ has any isolated vertices, set $j = 1$.
    - $1 \leq j < n/2$ and $G$ has $\geq j$ vertices of degree $\leq j$
    - so also $G'$ has $\geq j$ vertices of degree $\leq j$
- Now suppose $\delta(G)\geq 1$.
    - Since $G$ is not complete, there exists distinct vertices $u, v$, such that $uv\not\in{E(G)}$

Over all pair of distinct nonadjacent vertices,
choose $u, v$ to have maximum degree sum and label $u, w$, such that $d(u) \leq d(w)$.
- Since $u, w$ are nonadjacent and $G$ is a closure, $d(u) + d(w) \leq n -1$.
- Set $j = d(u)$, so $d(w)\leq (n-1) - j$
- Let $w = V(G)\setminus N[w]$ ([[Closed Neighbourhood]]). Note $u\in{W}$.
- For all $v\in{W}$, $w$ and $v$ are distinct and nonadjacent, so by choice of $u$, $d(v)\leq d(u)$.

![[Thm 6.11 Posa 2023-03-08 15.18.29.excalidraw]]

Since $\delta\geq 1$, $g\leq 1$.
Since $d(u) + d(w) \leq n-1$ and $d(u)\leq d(w)$,
$d(u)\leq (n-1)/2$, so $j < n/2$.
So, $1 \leq j \leq n/2$.
$|W| = |G| - |N[w]| = n-1-d(w) \geq n-1 - ((n-1) - j) = j$. 
$W$ is a collection of at least $j$ vertices of degree $\leq j$.
This was all in $G = C(G')$.
Degrees in $G'$ are $\leq$ degrees in $G$,
so $W$ is still a collection of $\geq j$ vertices of degree $\leq j$ (in $G'$)

## Example

![[Thm 6.11 2023-03-06 15.46.06.excalidraw]]

Degree sequence: 3, 3, 3, 3, 4
$n = 5$, $1 \leq j \leq 2$

| j   | \# vertices of degree less than j |
| --- | --------------------------------- |
| 1   | > 0                               |
| 2   | > 0                               |

Posa's theorem says $G$ is Hamiltonian.

