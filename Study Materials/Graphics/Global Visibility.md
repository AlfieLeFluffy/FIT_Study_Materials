---
tags:
  - PGR
aliases:
  - global visibility
---
Reasons for global visibility:
- Acceleration
	- Rendering only visible objects
	- Redrawing only necessary parts
	- Level of Detail
- Order of Rendering
	- Without a Z-Buffer
	- See-through objects
	- Other optical properties
- Effects
	- Rendering into textures
	- Shadows
	- Motion blur
## Acceleration
Redrawing only necessary parts is used only in 2D (is not used in 3D) and [[Hardware]] it recedes into background.
Rendering only visible objects allows to only render objects inside the field of view (by sides or near and far). It also allows to not render non-visible objects. This can be done through hierarchical division of the scene.
### Hierarchical Division
Hierarchical division can be done in one of many ways, such as:
- No hierarchy
- [[Tree|Trees]]
- Grids
- Combination
### Grouped Objects
Objects can be grouped within a scene and these groups can be put into a some sort of a hierarchy. This then allows to quicker and easier selection of objects to render and allows relevant objects to be rendered together.
These groups can be either:
- Bounding Spheres
- Oriented Bounding Box
- Axis-Aligned Bounding Box
- Slabs
### Binary Space Partitioning
This method involves dividing the scene in halves until all objects are inside the tree. The convention is that the scene is first divided vertically, then the half are divided horizontally, and their halves vertically and so on recursively. This can be done through BSP trees that can be:
- Axis-aligned
- Poligon-aligned
These trees are not flexible enough for dynamic rendering of scenes as the computation of BSP trees can take too long.
Another way of dividing the space is by using each node as a division of the space into two by a plane. This is mainly used in polygon aligned BSP trees and one helpful property is that if the scene is walked through from the back to the front the rasterization then can use the painter's algorithm without using a Z-Buffer. Each node can also store information about visibility of each object.
### Uniform Grids
Uniform grids have a rather effective walkthrough, but suffer from problems with details in too big of a scene.
### Octree
Octree has a relatively easy walkthrough and is adaptive, but it is not suitable for objects in a scene that are too far apart.
### Portals
Suitable for rendering of city-scape. A scene can be divided into cells (usually rooms) and windows or door (portals) connect these rooms together. This information can be used to create a set of potentially visible objects (PSV). 
Saved into each cell is:
- Walls of the cell
- All objects inside a cell
- Information about neighbouring cells
- Information about portals that connect them
There exist many methods for rendering of such structures.
## Rendering of Hidden Object
How to avoid rendering of hidden objects can be done several way depending on how the scene is divided.
### Binary Space Partitioning
For each view V, we can walkthrough it from the back to the front so the painter's algorithm can be used without a Z-Buffer. Into each node it can also be stored information about visibility of individual objects.
### Portals
With portals we can only render object that are in visible cells and ignore the rest.
## Occlusion Culling
The main goal of occlusion culling is to remove hidden objects from the scene during rendering to accelerate it. View-Frustrum culling gets rid of objects that are not in the visible field of view, Back-Face culling gets rid of triangles that are facing away from the camera and Occlusion Culling is trying to get rid of objects that are inside the view frustum, but are not visible as they are hidden behind other objects.
This can be done either precomputed or during runtime and there are [[Hardware]] occlusion queries and Hi-Z to figure this out.
### Hardware Occlusion Queries
Hardware occlusion queries uses proxy render + query to figure out if an object is visible or not. A catch with this is the better the object bounding is, the better the culling is, but that takes up more memory, so less complex the bounding is, the faster and less memory it takes.
### Hierarchical Z
A hierarchical Z-Buffer is a depth pyramid (max-depth 2x2 mipmap). It is build after a depth pre-pass and it is compute-driven culling with early-Z hardware rejection. 