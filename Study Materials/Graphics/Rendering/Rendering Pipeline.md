There are several components to make up the (programable) rendering pipeline.
## Components
1. **Vertex Assembly (Puller)** is a component on the graphics card that is responsible for reading stored data about points and putting them together to create a vertex. For this the puller uses several **reading heads**, with each one constructing one attribute of the vertex (position, normal, colour, etc...). The head move with a step called stride and some offset. They read the data from a byte array.
2. **Vertex Shader** is a programable component that takes vertex from the Assembly and transforms them by multiplying them with a **model matrix**, **view matrix** and a **projection matrix**. The input is vertexes in **model space** and output are vertexes in **clip space**. 
3. **Primitive Assembly** is a component that combines vertex into triangles (primitives). It waits for **3 vertexes** and constructs a triangle out of them.
4. **Clipping/Culling** handles clipping and culling of triangle so only those in the view frustum remain. Triangles on the edges of the frustum can be cut down to fit the space and triangles that are not visible are discarded.
5. **Perspective Division** transforms homogenous coordinates to Cartesian coordinates based on the depth of the triangle.
6. **Viewport Transformation** converts coordinates from NDC (normalized device coordinates **-1**, **+1**) to the resolution of the viewport so they could be rasterized.
7. **Rasterization** converts prepared triangles into fragments that get written into the framebuffer.
8. **Fragment shader** is a programable component that takes the fragments and colours them in based on their position in the triangle. For a specific fragment its barycentric coordinates are calculated and use interpolation of attributes from the primitive vertexes.
9. **Per-Fragment Operations** are two operation that are done for every fragment:
	1. **Depth Test** discards any fragments that are deeper then then what was already rasterized or if the fragment is closer (higher) it replaces the the original fragment with the new one.
	2. **Blending** instead of rewriting of the colour blends the original with the new one. This can be done in many ways, but is usually based on transparency.