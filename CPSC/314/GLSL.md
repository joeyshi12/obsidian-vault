# GLSL
- Reference: https://www.khronos.org/files/webgl20-reference-guide.pdf
- OpenGL shading language
- Used for both vertex shaders and fragment shaders with small differences

## Key Concepts
- Uniform type qualifier
	- Same for all vertices
- "in", "out" (WebGL 2) or "varying" (WebGL 1) type qualifiers configure data flow in pipeline
- "in" type qualifiers
	- Input from previous shader stage
	- For vertex shaders, these are per-vertex attributes
- "out" type qualifiers
	- Outputs to next stage