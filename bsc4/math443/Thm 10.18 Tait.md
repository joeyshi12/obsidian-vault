# Theorem 10.18 (Tait 1880)
The regions of a cubic map $G$ can be properly coloured with 4 or fewer colours
if and only if $\chi'(G) = 3$.

Observation:
$G$ is 3-reg; $\chi'(G)\in\{\Delta(G), \Delta(G) + 1\}$ [[Thm 10.12 Vizing]].
So, $\chi'(G)\in\{3, 4\}$.

## Proof
(=>) Colour regions of $G$ with colours $A, B, C, D$.
Map $AB$ or $CD$ to 1,
$AC$ or $BD$ to 2,
$AD$ or $BC$ to 3.

Every edge in $G$ is on the boundary of exactly 2 regions
because $G$ is bridgeless, so all edges are in a cycle.
Assign an edge a colour from $\{1, 2, 3\}$ based on colours of its incident regions and map.

(<=) Colour properly $E(G)$ with colours from $\{1, 2, 3\}$
Arbitrarily assign one region colour $A$ and colour remaining regions using map.