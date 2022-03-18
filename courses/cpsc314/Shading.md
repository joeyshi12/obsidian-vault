---
course: "cpsc314"
topic: "Shading 2 and PBR 1"
lecture: 17
chapters: [14]
---

## Toon Shading
Uses a small, discretized palette of colour and 'blackens' edges
For example, the intensity $I = \vec{n} \cdot \vec{l}$ can be discretized with $ceil(I\cdot k) / k$ for some $k\in\mathbb{N}$
To draw silhouette edges, we compute the fresnel $f = \vec{v} \cdot \vec{n}$ and blacken the fragment if
$f < \epsilon$ for some 'reasonable' $\epsilon$

![[Drawing 2022-02-28 10.13.38.excalidraw]]

## Blinn's change to the Phong Reflection
![[Drawing 2022-02-28 10.40.28.excalidraw]]
- Normal Phong: $I \propto \vec{B}(\vec{l}) \cdot \vec{v}$
- Blinn-Phong: $I \propto \vec{h} \cdot \vec{n}$
- In particular: $I = \max(0, \vec{h} \cdot \vec{n})^{\sigma}$

## Physically Based Renders
- Micro-geometry in fragment

![[Drawing 2022-02-28 10.47.48.excalidraw]]

- Account for optical properties of a surface
    - Photons may be reflected, diffused (emerge close to entry point), subsurface scattered, absorbed (gone), refracted (through)

![[Drawing 2022-03-02 10.10.36.excalidraw]]

## Metalness
Metalness: $M\in [0, 1]$
$M = 0$ means the surface is dielectric (skin, plastic)
$M = 1$ means the surface has good conduction (gold, steel)

https://threejs.org/docs/scenes/material-browser.html#MeshStandardMaterial

**Metalness/Roughness can be packed into a single texture, pass these as with other maps**
- .roughnessMap: Texture
    - The green channel of this texture is used to alter the roughness of the material
- .metalnessMap: Texture
    - The blue channel of this texture is used to alter the metalness of the material