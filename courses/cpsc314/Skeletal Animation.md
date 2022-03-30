---
course: "cpsc314"
title: "Skeletal Animation"
---


## Steps
1. Animate the skeleton
2. Deform/move skin to follow


## Simple Case: 2-joint arm
- Each joint has a coordinate frame
- A bone in Threejs is essentially an `Object3D`
- A skeleton/armature is essentially a scene graph

![[Pasted image 20220330101405.png|500]]

## Animate
![[Pasted image 20220330101946.png|700]]
- $a \approx$ animation or after
- $b \approx$ before or *bind* pose

The bind matrix is the matrix world for a particular bind pose

![[Pasted image 20220330103711.png|600]]

$\overline{x}_{2b} = \overline{x}_{2a}$
$\overline{x}_{2b} = \overline{\underline{B}}_{2w}^{-1} \overline{x}_{wb}$ 
$\overline{x}_{wa} = \overline{\underline{A}}_{2w}\overline{\underline{B}}_{2w}^{-1} \overline{x}_{wb}$  (key skinning equation)

**Define**:  $T[2] = A_{2w}B_{2w}^{-1}$
- The inverse bind matrix $B_{2w}^{-1}$ is precomputed **once**
- The animation matrix $A_{2w}$ is computed once per time step/"frame"

**Implementation**:
1. Compute $T[k]$ for $k$ bones once per time step in js code
2. Pass as uniforms to the vertex shader
3. Evaluate $\overline{x}_{wa} = A_{kw}B_{kw}^{-1}w_{wb}$ on vertex shader
