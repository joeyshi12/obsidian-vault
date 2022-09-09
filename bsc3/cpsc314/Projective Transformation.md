---
course: "cpsc314"
topic: "Projective Transformations"
chapters: [10.3, 11.2, 11.3]
---

Given a point, $\tilde{p}$ in the scene with eye coordinates $[x_e, y_e, z_e, 1]^t$ and film plane at $z = -1$,
we can project it onto the film plane by taking
$x_n = -\frac{x_e}{z_e}$, $y_n = -\frac{y_e}{z_e}$ (similar triangles)

![[Pasted image 20220317202513.png]]

This can be modeled with a transformation of the form
$$
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
- & - & - & - \\
0 & 0 & -1 & 0 \\
\end{pmatrix}
\begin{pmatrix}
x_e \\ y_e \\ z_e \\ 1
\end{pmatrix}
= \begin{pmatrix}
x_c \\ y_c \\ z_c \\ w_c
\end{pmatrix}
= \begin{pmatrix}
x_nw_n \\
y_nw_n \\
- \\
w_n
\end{pmatrix}
$$
The output of the matrix multiply $\overline{p_c}$ is called the *clip coordinates* of $\tilde{p}$. 
To extract $x_n$, we can perform a perspective divide: $\displaystyle x_n = \frac{x_c}{w_n} = \frac{x_n w_n}{w_n}$

The output $\overline{p_n}$ is called the *normalized device coordinates* of $\tilde{p}$

## Scaling
If we want to move our film plane to $z_e = n$ for some negative $n$, then $\displaystyle x_n = \frac{x_e n}{z_e}, y_n = \frac{y_e n}{z_e}$.
So, our projection matrix becomes

$$
\begin{pmatrix}
-n & 0 & 0 & 0 \\
0 & -n & 0 & 0 \\
- & - & - & - \\
0 & 0 & -1 & 0 \\
\end{pmatrix}
\begin{pmatrix}
x_e \\ y_e \\ z_e \\ 1
\end{pmatrix}
= \begin{pmatrix}
x_c \\ y_c \\ z_c \\ w_c
\end{pmatrix}
= \begin{pmatrix}
x_nw_n \\
y_nw_n \\
- \\
w_n
\end{pmatrix}
$$
In the vertex shader, the projection is applied after the model view matrix. The perspective divide and viewport transform is applied in the fixed function hardware. [[Projection and Viewport Transformations]]
$$
\overline{x}_o \xrightarrow{VM} \overline{x}_e \xrightarrow{P} \overline{x}_c \xrightarrow{perspectiveDivide} \overline{x}_n \xrightarrow{viewportTransform} \overline{x}_w
$$