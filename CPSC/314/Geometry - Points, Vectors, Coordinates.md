# Vectors and Linear Algebra
- An algebra is a set of objects $V$ and operations defined over $V$
	- Objects: vectors, operations: \*, +
- Basis: linearly independent set of vectors that can generate all vectors in the space

## Coordinates in a basis $\vec{b}$
For any vector $\vec{v}$ in the space, we can write $\vec{v} = v_0\vec{b_0} + v_1\vec{b_1}$
This can be shortened to
$$
\vec{v}

= \left(\begin{array}{cc}
\vec{b_0} & \vec{b_1}
\end{array}\right)

\left(\begin{array}{c}
v_0 \\
v_1
\end{array}\right)

= \underline{\vec{b}}\overline{v}
$$
$v_0$, $v_1$ scalars can be in array, in column matrix $$\vec{v} \to_{\vec{b}} \binom{v_0}{v_1} = \overline{v}$$
We denote a row of items $\underline{a} = (a_0, a_1)$

##  Representing points
- We extend addition to include adding a point and a vector
- We call $(\vec{b_1}, \vec{b_2}, \vec{b_3}, \tilde{b_0})$ the coodinate frame, where $(\vec{b_1}, \vec{b_2}, \vec{b_3})$ is a basis and $\tilde{b_0}$ is the origin point
- We call $(p_1, p_2, p_3, 1)^T$ homogeneous coordinates of a point
- We call $(v_1, v_2, v_3, 0)^T$ homogeneous coordinates of a vector
- $\tilde{p} = \underline{\tilde{b}} \overline{p}$

![[Pasted image 20220119102202.png]]

## Important coordinate frames in graphics
- World coordinate frame $\underline{\vec{w}} = (\vec{w_1}, \vec{w_2}, \vec{w_3}, \tilde{w_0})$
- Model frame (object frame / frame of  model in its object file) $\underline{\vec{b}} = (\vec{b_1}, \vec{b_2}, \vec{b_3}, \tilde{b_0})$
- Camera frame $\underline{\tilde{c}}$
- Transform from model frame to world coordinate: multiply coordinate by `modelMatrix`
	- $\tilde{p} = \underline{\tilde{w}} \overline{\underline{M}} \overline{p}$
- World frame to camera frame: `viewMetrix`
	- $\tilde{p} = \tilde{\underline{c}}\overline{\underline{V}}\overline{p}$
- `modelViewMatrix = viewMatrix * modelMatrix` 
- $\tilde{p} = \underline{\tilde{c}} \overline{\underline{V}} \overline{\underline{M}}\overline{p}$