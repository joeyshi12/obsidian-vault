# Cor 6.7 (Dirac)
Let $G$ be a graph with $\delta(G) \geq |G| / 2$, $|G| \geq 3$.
Then, $G$ is Hamiltonian.

## Proof
In such a graph, $d(x) + d(y) \geq |G|$ for any $x, y\in{V(G)}$ (adjacent or not).

## Note
Dirac's theorem was proved before Ore's. Both proofs' bounds are the best possible.
Vocab: A vertex $v$ in $G$ is **dominating** if $N(v) = V(G)\setminus\{v\}$.
Let $G$ consist of $K_a\cup K_b$ plus a dominating vertex.

If $x, y$ are distinct, nonadjacent, then $d(x) + d(y) = a + b = |G| - 1$.
The dominating vertex is a cut vertex, so $G$ is not Hamiltonian.
Same example works for Dirac: $a = \lfloor\frac{|G| - 1}{2}\rfloor$, $b = \lceil\frac{|G| - 1}{2}\rceil$.