## Theorem 6.6 (Ore)
Let $G$ be a graph of order at least $3$.
For all pairs of distinct, nonadjacent vertices $x$, $y$,
$$d(x) + d(y) \geq |G|.$$
Then, $G$ is Hamiltonian.

## Proof (contrapositive)
Let $G$ be non-Hamiltonian and $|G| \geq 3$.
Construct $G'$ from $G$ by adding (one-by-one) edges to $G$
until the addition of any edge would make the graph Hamiltonian.

*Note: we will show there exists distinct nonadjacent vertices $x$, $y$, such that
$d_{G'}(x) + d_{G'}(y) < |G|$, so
$d_G(x) + d_G(y) \leq d_{G'}(x) + d_{G'}(y) < |G|$*.
Then, we are done.

From now on, degrees refer to $G'$.
If $G'$ is complete, it is Hamiltonian, so $G'$ is not complete,
so there exists nonadjacent vertices $x, y$.
By contruction of $G'$, $G' + xy$ is Hamiltonian.
Then, $G'$ has a Hamiltonian path $P$ with endpoints $x$, $y$.

Label vertices of $P$ in order as: $x=x_1, x_2,\dots, x_{n-1}, x_n = y$.
Let $i\in\{1,\dots, n-1\}$. If $xx_i\in{E(G')}$, then $yx_{i-1}\not\in{E(G)}$.
- If $i=1$, vacuously true: $xx_1 = xx\not\in{E(G)}$.
- If $i=2$, $xx_2\in{E(G)}$. By assumption, $yx_1\not\in{E(G)}$ because $x, y$ are nonadjacent.
- If $i > 2$, if $xx_i$ and $yx_{i-1}$ are both edges in $G'$, then $G'$ has a Hamiltonian cycle.
    - $xPx_{i-1}yPx_{i}x$ is a Hamiltonian cycle

Using the claim: $N(y) \subseteq V(G)\setminus\{y\}$.
$d(y) \leq (n-1) - d(x)$ (for every neighbour of $x$, there is a non-neighbour of $y$ in $\{x_1,\dots, x_{n-1}\}$)
So, $d(x) + d(y) \leq |G| - 1$.

![[Thm 6.6 2023-03-06 15.13.47.excalidraw]]

