## OpenGL Pipeline
- Shapes are "discretized" into triangles, line segments, etc...
- Triangles defined by positions of their vertices

![[Pasted image 20220114100801.png]]

## Vertex Shader
- Vertices are stored in a vertex buffer
- When the draw function is called, the vertices pass through the vertex shader
- On input to the vertex shader, each vertex (black) has associated attributes
- One output, each vertex (cyan) has a value for `gl_Position`
![[Pasted image 20220112104338.png]]

## Rasterization
- The data in `gl_Position` are used to place the three vertices of the triangle on a virtual screen.
- The rasterizer figures out which pixels (orange) are inside the triangle and interpolates the varying variables from the vertices to each of these pixels

![[Pasted image 20220114101910.png]]

## Fragment Shader
- Each pixel (orange) is passed through the fragment shader which computes the final color of the pixel (red)

![[Pasted image 20220114102149.png]]

- By changing the fragment shader, we can simulate light reflecting off of different kinds of materials.

![[Pasted image 20220114102317.png]]