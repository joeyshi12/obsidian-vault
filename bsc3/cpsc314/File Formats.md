---
course: "cpsc314"
title: "File Formats"
---

## Obj Format

Only stores the geometry
- Vertex position, UV, normal
- Faces

```obj
# Vertex positions
v 0.123 0.32 1.0
v ...

# Vertex normals
vn 0.707 0.000 0.707
vn ...

# Vertex something...
vp 0.310000 3.210000 2.100000
```

## glTF Format

- Version 1.0 (2015) has limitations, version 2.0 (2017) is much more encouraged
- JSON formatted storing information about the scene graph + textures + animation assets
    - A scene is made up of nodes, where nodes is an `Object3D`
    - A node may represent a mesh, where the mesh contains all the vertex data
    - https://www.khronos.org/files/gltf20-reference-guide.pdf

## glTF Features

- A node may also be a 'skin'. Skins contains an array of joints for defining a skeleton hierarchy