---
course: "cpsc314"
title: "Shadows"
chapters: [11, 15]
---

## Visibility
Shoot ray from camera.
We can store everything along the ray and compute the closest
This makes sense in ray tracing where we are working one pixel per ray at a time,
but not for OpenGL, where we work one triangle at a time
```python
def rayCasting(...):
    for all screenPixels:
        for all objects:
            compute intersection
        return closest point

def depthBuffer(...):
    for all objects:
        for all fragments: # or pixels
            record depth
        return closest
```

## Shadow mapping
If a point observed by the eye is not observed by the light,
there muse be some occluding object in between and we should draw the point as if it were in a shadow

![[Pasted image 20220307103943.png|700]]

