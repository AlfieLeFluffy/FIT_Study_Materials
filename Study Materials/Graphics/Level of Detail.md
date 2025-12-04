---
tags:
  - PGR
aliases:
  - level of detail
---
The main idea behind level of detail is to reduce the rendering cost of objects that are far away and their details are not necessary and would be lost in the final scene, which is done to save resources.
## Selection
Selection of the level of detail for an object can be done through:
- **Distance**, which is rather effective
- **Size** which can be done through a bounding cube or sphere and is independent of the resolution. 
- **Priority**
## Model Simplification
There are several ways to simplify a model for several levels of detail, such as:
- **Decimation**
- **Edge Collapse** (Vertex Split)
- **Progressive Meshes** (Hugues Hoppe)
	- A model can be encoded as a super simple net with a series of vertex-split operations.
### Billboarding
Billboarding is a simple technique where a 3D object is represented through a 2D sprite when looked from far enough. This sprite is only from one angle/
### Impostors
Impostors are a more advanced version of Billboarding where the object has a 2D sprite from several angle and thus can be viewed from a distance from these angles.
### Height Maps
Height maps are an easy way to implement many things from terrain to details on models. The main idea is to have the texture and a height map (a picture with each pixel being on a gradient from black to white) and then during rendering the the position of the texture is offset in the third dimension by the amount specified in the height map, with white being the most and black being the least.
### Dynamic Height Maps
Dynamic height maps are an upgraded versions of the normal height maps that can be changed/deformed during runtime, which can create effects such as leaving tire marks in mud.
## Algorithms
There are many algorithms for working with / deciding level of detail, but most prominent are:
### ROAM
Algorithm ROAM works with binary triangle trees that can split, force split or merge triangles of objects to achieve desired level of detail based on the current need.
### Chunked LOD
Chunked LOD uses quadtrees to split the desired model into four quadrants (recursively can go lower). These quadrants can then be worked with individually and their level of detail can be adjusted. This is also applied to texturing but can create a problem of tiles that are not touching (skirts).
Advantages:
- Effective use of triangles in blocks.
- LOD of textures is integrated with geometry LOD.
- Easy binding onto external memory.
- Vertices do not "jump." 
- Low CPU requirements.
Disadvantages:
- Pre-rendering
- Static height map
- Memory usage
## Foveated Rendering
Foveated rendering works on (reproduces) the same principle that human sight does. Objects onto which the eye is focusing are in greater detail that object in the peripheral vision. This can be mainly used in VR/AR and requires eye tracking through sensors inside the glasses to work. The area upon which the eyes are looking is then rendering in full quality, while other areas are rendering in less (60% resolution near the point, 20% resolution for peripheral).
Advantages:
- High amount of optimization for rendering
- With correct use the user does not notice it
Disadvantages:
- Cost
- Saccadic eye movements
- Implementation into existing applications