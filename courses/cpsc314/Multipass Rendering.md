---
course: "cpsc314"
title: "Multipass Rendering"
---

## Multipass Rendering
1. Create "render target" and create a scene to render to, as with frame buffer
    1. `const renderTarget = new THREE.WebGLRenderTarget(rtWidth, rtHeight);`
2. Use image data in the render target as a texture
    1. `const material = new THREE.MeshPhongMaterial({map: renderTarget.texture})`
3. In animation loop/update, first render to the render target
4. Finally render the scene to frame buffer that uses the render target texture

*If the render target is null, the renderer's render target is the frame buffer*

## Tips
- Check out `THREE.DepthTexture` (saves depth when using render target)
    - Use renderTarget.depthTexture as the shadow map
- How to set
    - lightProjMatrix and lightViewMatrix
    - Remember that after Projection Matrix and "perspective divide" (not needed for the directional light/orthographic camera), fragment position is in NDC (normalized device coordinates)