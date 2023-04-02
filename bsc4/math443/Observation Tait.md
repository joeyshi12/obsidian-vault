
# Observation (Tait)
If all regions of all 3-regular plane graphs can be properly coloured with $\leq 4$ colours,
then the regions of all planar graphs can be coloured with $\leq 4$ colours.

## Justification
Given planar $G$, we'll make a 3-regular planar graph $G'$.
If $G'$ has a proper 4-colouring of its regions, then $G$ does too.

1. If there exists $v\in{V(G)}$, such that $d(v)\in\{0, 1\}$, delete it
2. If there is a vertex $v$ in remaining graph of degree $\geq 4$:
    1. draw tight circle around $v$ (circle intersects all edges incident to $v$, no vertices, no other edges)
    2. if there exists a vertex of degree 2, delete, replace with edge, endpoints $N(v)$
    3. create a vertex where circle intersects edges
    4. delete $v$

$G'$ is $3$-regular.
Properly 4-colour its regions
Consider "adding back" vertices to get $G$.
If $v$ was a high-degree vertex:=.
Shrink circle region back down to a vertex its colour deleted regions around circle keep colours.
If $v$ had degree $\leq 2$. Addin