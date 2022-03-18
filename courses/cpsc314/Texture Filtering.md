---
course: "cpsc314"
title: "Texture Filtering"
---

Why access texture values using things called "Sampler2D", "SamplerCube", etc...?

## Texture Magnification
**Reconstruction**
Given a discrete image $I[i][j]$, how do we create a continuous image.
How to get a texture colour between texels?
This process is called *reconstruction*
Key idea: interpolation/compute in-between values (e.g. constant interpolation, linear interpolation)

![[Pasted image 20220309101707.png|700]]
![[Pasted image 20220309101750.png|700]]
![[Pasted image 20220309101903.png|700]]

## Linear and Bilinear Interpolation
Bilinear interpolation (2D) is computed here by taking the linear interpolations
from $p_{01}$ to $p_{11}$ and $p_{00}$ and $p_{10}$. Then, we take the linear interpolation between the previous 2 lines at $p_0 = x$ 

![[Pasted image 20220309102258.png|700]]

## Texture Minification
Problem: **aliasing**
Notice how the squares father in the image is much more noisy
This problem is caused by **too much information in one pixel**

The solution is to take the average/blur (anti-aliasing)

![[Pasted image 20220309103052.png|400]]

![[Pasted image 20220309103805.png|400]]

**Mip Mapping**
- Start with n original texture $T^0$ and then creates a series of lower and lower resolution (blurrier) texture $T^i$
- Each successive texture is twice as blurry.
    - Because they have successively less detail, they can be represented with 1/2 the number of pixels in both the horizontal and vertical directions
- Given a texel coordinate $(x, y)$ for a version of the image with scale $N\times N$, we can interpolate between the in-between scales shown in the image below

![[Pasted image 20220309104438.png|700]]

**Three.js**
- Set `Texture.minFilter` to `THREE.LinearMipMapLinearFilter`
- Trilinear interpolation requires WebGL to fetch 8 texture pixels and blend them appropriately for every requested texture access

## Sampling in 1D
$$
\frac{1}{L}\int I(x) \approx \frac{1}{N} \sum I[x]
$$

![[Pasted image 20220311103546.png]]

## Terminology
Assume 4 sampling points for each pixel
- Over-sampling: for every fragment picking more than one colour sample and
- Super-sampling: run fragment shader on **all 4** samples and the results of these are averaged to get the final result
- Multi-sampling: depth and stencil tests run on all 4 samples and the fragment shader is run **once** on a sample that passed the depth and stencil tests. The color value is copied to all other samples that passed the depth and stencil tests. The same operation may be applied multiple times if multiple fragments overlap for 1 pixel (such as on edges). Finally, average all samples to get final result