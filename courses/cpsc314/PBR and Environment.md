---
course: "cpsc314"
title: "PBR & Environment"
---

## Environment Cube Maps
- Texture maps can be used to model the environment around the rendered object.
    - A **Sky Box** uses 6 square textures for the faces of a large cube surrounding the scene.
    - GLSL cube-texture data type: `samplerCube`
- Cube mapping
    - The samplerCube will let you access the colour based on the direction the camera is looking at.
![](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse4.mm.bing.net%2Fth%3Fid%3DOIP.DVy4vKajGXifC6zLtzlDhQHaFm%26pid%3DApi&f=1)

If you treat an object as a perfect mirror, you can compute the bounce vector of the view direction to determine the background texture that will be reflected on the object. `-vPosition` is the view vector $\vec{v}$

![[Pasted image 20220304104623.png|500]]

```
uniform samplerCube uTexUnit0;
in vec3 vNormal;
in vec4 vPosition;
out vec4 fragColor;

vec3 reflect(vec3 w, vec3 n) {
    return n*(dot(w, n) * 2.0) - w; // bounce vector
}

void main() {
    vec3 normal = normalize(vNormal);
    vec3 reflected = reflect(normalize(vec3(-vPosition)), normal);
    vec4 textColor0 = samplerCube(uTexUnit0, reflected);
    fragColor = vec4(texColor0.r, textColo0.g, textColor0.b, 1.0);
}
```

![[Pasted image 20220304104917.png|500]]