---
course: "cpsc314"
title: "Spines and Morphing"
chapters: [9]
---

## Splines
- Have control points and smoothly blends between them
    - Like interpolation in  [[Animation]]

**Linear Blending Function**
$$t = \frac{s - s_i}{s_{i+1} - s_i}$$
![[Drawing 2022-03-28 10.12.26.excalidraw]]

## Higher Order Interpolations
- *Sweet spot* is cubic
- For animation, we want our piecewise intepolation to be smooth at every point
    - So, we want to control the tangents at the ends of each interval

    
## Hermite Intepolation
Specify control points at 2 ends and the tangents
The simplest curve that can encode this info is the **cubic**
$p(t) = p_0 + p_1 t + p_2 t^2 + p_3 t^3$
$p'(t) = p_1 + 2p_2 t + 3p_3 t^2$
$p(0) = c_0$
$p(1) = c_1$
$p'(0) = d_0$
$p'(1) = d_1$

![[Drawing 2022-03-28 10.20.06.excalidraw]]

## Bezier Curves
- $C_0, C_3$ interpolated and $C_1, C_2$ approximated

![[Drawing 2022-03-28 10.29.04.excalidraw]]


## Catmull - Rom Splines
- Approximate with center difference

![[Drawing 2022-03-28 10.34.01.excalidraw]]

![[Pasted image 20220328104127.png|500]]
