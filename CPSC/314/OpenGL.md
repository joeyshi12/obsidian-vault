# Open Graphics Library
- Open industry-standard API for hardware accel graphics drawing
- OpenGL ES = embedded systems version of OpenGL with reduced functions
- WebGL is based on Open GL ES and makes OpenGL accessible from Javascript

## OpenGL Pipeline
- Shapes are "discretized" into triangles, line segments, etc...
- Triangles defined by positions of their vertices

## OpenGL Pipeline: Vertex Shader
- Vertices are stored in a vertex buffer
- When the draw function is called, the vertices pass through the vertex shader
- On input to the vertex shader, each vertex (black) has associated attributes
- One output, each vertex (cyan) has a value for `gl_Position`
![[Pasted image 20220112104338.png]]