## Corollary 6.2
A connected graph has an [[Eulerian Trail]] iff exactly 2 vertices have odd degree.
Futhermore, those 2 vertices are the endpoints of the trail.

## Proof
If $G$ has an Eulerian trail: impose a direction.
Interior vertices have (in-degree) = (out-degree).
End points have (in-degree) = (out-degree)$\pm 1$.
So, endpoints have odd degree in $G$, all other vertices even.

Suppose $G$ connected and $x$, $y$ are the unique 2 vertices of odd degree.
Create $G'$ by adding a new vertex $z$ adjacent only to $x$ and $y$.
All vertices of $G'$ have even degree (and $G'$ nontrivial, connected).
So, by [[Thm 6.1]], $G'$ has an Eulerian trail of $G$ with endpoitns $x, y$.

![[Cor 6.2 Eulerian Trail 2023-03-03 15.21.43.excalidraw]]