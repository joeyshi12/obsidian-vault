---
course: "cpsc314"
title: "Animation"
lecture: 27
---

Key frames are often manually set
Software interpolates/blend between key frames

## Interpolation
![[Drawing 2022-03-25 10.22.47.excalidraw|300]]

Suppose we have the following data points: $(0, C_0), (1, C_1), (2, C_2), ...$
Linear interpolation gives us $C(t) = C_0(1 - t) + C_1 t$ for the first segment

Local support: control points do not affect things far away

![[Drawing 2022-03-25 10.35.38.excalidraw]]

We can introduce another function to smooth the previous interpolation
$C(t) = \sum_{i=0}^{n} C_i\phi_i(t)$

**Generalizations**
- Higher dimensions: just apply to each coordinate
- Key frame animation (just a high dimensional "pose space")
- Smoother interpolation
    - Replace $\phi_i$ with smoother functions (e.g. piecewise polynomials)

We require $\sum_{i=0}^{n} \phi_i = 1$ for all $t$

**Check:**
Linear: $(1 - t) + t = 1$
Quadratic: 