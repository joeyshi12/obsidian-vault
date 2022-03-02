---
course: "cpsc314"
topic: "Shading 2 and PBR 1"
lecture: 17
chapters: [14]
---

## Toon Shading
- Use a small, discretized palette of colour
![[Drawing 2022-02-28 10.13.38.excalidraw]]
- Draw silhouette edges
    - Example: when  $\vec{n} \cdot \vec{v} \approx 0$ set the colour to $0$

## Blinn's change to the Phong Reflection
![[Drawing 2022-02-28 10.40.28.excalidraw]]
- Normal Phong: $I \propto \vec{B}(\vec{l}) \cdot \vec{v}$
- Blinn-Phong: $I \propto \vec{h} \cdot \vec{n}$
- In particular: $I = \max(0, \vec{h} \cdot \vec{n})^{\sigma}$

## Physically Based Renders
- Microgeometry in fragment

![[Drawing 2022-02-28 10.47.48.excalidraw]]