---
course: "cpsc314"
title: "Texture Mapping"
lecture: 16
chapters: [15]
---

## How to model the earth?
Use longitude and latitude (e.g. for Vancouver, $\overline{u} = \left[\begin{array}{cc}49 & -123\end{array}\right]^T$)
Texture coordinates are denoted as "$u, v$"
*uv is a built-in varying variable in threejs*
$$\overline{u}
= \left[\begin{array}{c}u \\ v\end{array}\right]
= \left[\begin{array}{c}49 \\ -123\end{array}\right]$$

## Texture mapping
- Bunch of WebGL functions to load a texture and set various parameters (lin/const, mipmap, wrapping rules).
- A uniform variable is used to point to the desired texture unit.
- Varying variables are used to store texture coordinates


## Steps for texture mapping
1. Create a *texture object* and load texels into it
2. Include *texture coordinates*  with your vertices
    1. Texture coordinates can be computed in the shader itself (computed procedurally)
3. Associate a *texture sampler*  with each texture map used in shader
4. Retrieve texel value
