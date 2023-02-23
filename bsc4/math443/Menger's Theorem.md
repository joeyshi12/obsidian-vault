# Menger's Theorem
Let $u$ and $v$ be nonadjacent vertices in a graph $G$. Then,
$\kappa(u, v) = \lambda(u, v)$

## Proof
Already covered $\kappa(u, v) \geq \lambda(u, v)$.
$k = \kappa(u, v) \leq 1$
Induction on $\|G\|$.

Consider a graph $G$, such that $\kappa(u, v) = k \geq 2$.
We want to find a collection of $k$ internally disjoint $u-v$ paths (Then $\lambda \geq \kappa(u, v)$).

**Case 1**: There exists minimum $u-v$ separating set $W$ and there exists $w\in W$, such that $w\in{N(u)\cap N(v)}$
*Finished last time (check last few pages in notebook)*

**Case 2**: There exists minimum $u-v$ separating set $W$, such that $W\not\subseteq N(u)$ and $W\not\subseteq N(v)$
i.e., both $u$ and $v$ have a non-neighbour in $W$ (might not be the same non-neighbour).

Define $G_u$ as the subgraph of $G$ consisting of all $u-w$ paths with no internal vertices from $W$.
Define $G_v$ similarly.
We showed $V(G_u)\cap V(G_v) = W$.

Define $G_u'$ to be the graph obtained from $G_u$ by adding a new vertex $v'$ whose neighbourhood is $W$.

Observations about $G_u'$
1. $\|G_u'\| < \|G\|$
    - To make $G_u$ from $G$, we deleted every edge of $G_v$. In particular, we deleted $w-v$ path for every $w\in{W}$.
    - So, we deleted at least $k$ distinct edges (with one endpoint in $W$).
    - By case 2, at least 1 $W-v$ path had at least 2 edges, so actually, we deleted at least $k+1$ edges from $G$ to make $G_u$.
    - So, $\|G_u'\| < \|G\|$.
    - ![[Menger's Theorem 2023-02-17 15.21.49.excalidraw|200]]
2. $W$ is a minimum $u-v'$ separating set in $G_u'$..
    - $W = N(v')$, so $v'$ is isolated in $G_u - W$. So, $W$ separates $u$ and $v'$. 
    - To see that it has minimal size, consider an arbitrary $u-v'$ separating set in $G_u'$ called $Z$.
    - In $G_u' - Z$, $u$ and $w$ are in different components for every $w\in{W\setminus Z}$.
    - Every $u-v$ path in $G$ uses a vertex of $W$, so deleting $Z$ from $G$ disconnects every $u-v$ path, so $Z$ is a $u-v$ separating set in $G$
    - So, $|Z| \geq k$. Since $|W| = k$, $W$ is a minimum $u-v'$ separating set in $G_u'$

By observation 1 and 2, the inductive hypothesis says
there exists a collection of $k$ internally disjoint $u-v'$ paths in $G_u'$.
By symmetry, there exists a collection of $k$ internally disjoint $v-u'$ paths in $G_v'$.
Deleting $u'$ and $v'$ from the paths in these collections gives us a collection of internally disjoint paths
$\forall w\in{W}, \exists u-w$ path and a $u-v$ path.
Gluing them together gives a collection of $k$ internally disjoint $u-v$ paths.

![[Menger's Theorem 2023-02-17 15.33.18.excalidraw]]

**Case 3**: Not case 1 nor case 2
Let $W$ be an arbitrary minimum $u-v$ separating set.
Let $w\in{W}$.
- If $w$ is adjacent to both $u$ and $v$, case 1
- If $w$ is adjacent to neither $u$ not $v$, case 2

So, every vertex in $W$ has exactly 1 neighbour in $\{u, v\}$.
Let $w, w'\in{W}$ be distinct.
If $w\in{N(u)}$ and $w'\in{N(v)}$, then $w\not\in{N(v)}$ and $w'\not\subseteq N(u)$. This is again case 2.

So, in case 3, $w\subseteq{N(u)\setminus N(v)}$ or $w\subseteq N(v)\setminus N(u)$.

WLOG assume $W\subseteq N(v)\setminus N(u)$.
Let $P$ be a shortest $u-v$ path.
Every $u-v$ path has a vertex from $W$.
No vertex of $W$ is adjacent to $u$.
So, we can write $P = uxy\cdots v$, where $u, x, y, v$ are all distinct.

![[Menger's Theorem 2023-02-17 15.40.47.excalidraw|300]]

Name $e = xy$.
Claim: $G - e$ has a minimum $u-v$ separating set of size $k$.
Once claim is proved, $\|G - e\| < \|G\|$, so by induction hypothesis,
there exists a collection of $k$ internally disjoint $u-v$ sets ... DONE.

## Proof of claim
Suppose BWOC, there exists $u-v$ separating set $Z$ in $G-e$, such that $|Z| < |W|$.
- Note $u, v\in{(G - e) - Z}$, so $u, v\in{G - (Z + x})$
- $G - (Z + x)\subseteq (G - e) - Z$, $(G - e) - Z$ is $u-v$ separated.

So, $Z + x$ is a $u-v$ separating set in $G$,
so $|Z + x| \geq k$, so $|Z| \geq k+ 1$.
Then, since $|Z + x| = k$, $Z + x$ is a minimum $u-v$ separating set in $G$.
By symmetry, also $Z + y$ is a minimum $u-v$ separating set in $G$.
Since $k \geq 2$, $|Z| \geq 1$.
By case assumptions, since $x\in{N(w)}$, then $Z\subseteq N(u)$.
Then, since $Z + y$ is a minimum $u-v$ separating set,
and $Z \subseteq N(u)$, by case assumptions, $y\in{N(u)}$. CONTRADICTION.

So, $P = uxyv$