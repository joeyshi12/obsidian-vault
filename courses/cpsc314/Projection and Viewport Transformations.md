---
course: "cpsc314"
topic: "Some Remaining Vertex Shader Topics"
lecture: 13
---

![[Pasted image 20220209100947.png|700]]

## General Projective Transformation
- View frustum to box whose size depends on view frustum
- We can scale and shift that box to make it a standard size, with each coordinate from -1 to +1
![[Drawing 2022-02-09 10.12.53.excalidraw|900]]

$$
\left[\begin{array}{c}
x_n w_n \\ y_n w_n \\ z_n w_n \\ w_n
\end{array}\right]
=
\left[\begin{array}{c}
x_c \\ y_c \\ z_c \\ w_c
\end{array}\right]
=
\left[\begin{array}{cccc}
s_x & 0 & -c_x & 0 \\
0 & s_y & -c_y & 0 \\
0 & 0 & \frac{f+n}{f-n} & -\frac{2n}{f-n} \\
0 & 0 & -1 & 1
\end{array}\right]
\left[\begin{array}{c}x_e \\ y_e \\ z_e \\ 1\end{array}\right]
$$

## Path from vertex to pixel
![[Pasted image 20220209103619.png|700]]

## Viewport
- We think of each pixel as owning the real estate which extends 0.5 pixel units in the position and negative, horizontal and vertical directions from the pixel center.

![[Pasted image 20220209103959.png|700]]

## Viewport Matrix
After the [[Projective Transformation]] and perspective divide into NDC, the viewport matrix maps to window coordinates. 
We need a transform that maps the lower left corner to $[-0.5, -0.5]^t$ and upper right corner $[W - 0.5, H - 0.5]^t$
$$
\begin{pmatrix}
x_w \\ y_w \\ z_w \\ 1
\end{pmatrix}
= \begin{pmatrix}
W/2 & 0 & 0 & (W-1)/2 \\
0 & H/2 & 0 & (H-1)/2 \\
0 & 0 & 1/2 & 1/2 \\
0 & 0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
x_n \\ y_n \\ z_n \\ 1
\end{pmatrix}
$$
