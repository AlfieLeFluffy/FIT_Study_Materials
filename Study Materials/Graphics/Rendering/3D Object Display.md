To display a 3D object we usually use a 2D plane through a process called **projection** (transformation of 3D to 2D, which means loss of data). The display (window) then become a **viewport**. To project an object we use so called **projection rays**. In computer graphics we most often use triangles to rasterize 3D objects as they are convex and their calculations can accelerate rather well in [[Hardware (HW)]].
## Components of a 3D Scene
- **Near Clip Plane** defines the minimal distance an object has to be away from the camera (minimal depth) in order for the camera to render it.
- **Far Clip Plane** defines the maximum distance an object has to be away from the camera (maximum depth) in order for the camera to render it.
- **Viewport Frustum** is a space in model space that will appear on the screen.
- **Viewport** is a place from which we observe the scene.
- **Light** can be either point or surface (plane) and defines the visibility of objects and their properties such as colour, shadow, etc.
- **Model Objects** 
## Parallel (Orthographic) Projection
This projection keeps the size of the objects the same regardless of how far away from the viewport they are.
### Properties
- Keeps lines parallel to each other.
- The distance of the viewport does not influence the size on the resulting image.
- Orthogonal projection means that the projection rays run perpendicular to the viewport.
- It is commonly used in technical applications such as **CAD** and other documenting programs.
## Perspective (Center) Projection
This perspective draws objects further away from the viewport smaller.
### Properties
- Does not keeps lines parallel to each other.
- The distance of the viewport does influence the size on the resulting image.
- Non linear center projection means that all projection rays travel out of one point (the center of projection), then through the viewport and onto the scene.
- To ease the manipulation with the camera it is usually fixed in place at the start of the coordinate system and the scene moves instead through [[Geometric Transformation]]s.
- **Geometric Projection Princip** - From the points (peaks) of triangles in the scene are projected rays towards the viewport (in perspective towards the center). In the places the ray intersects with the **viewport** is the place the we rasterize the point representing the place.
## Raytracing
It is a method for realistic looking scene projection. It uses backwards tracking of light rays from the camera to the source of light and it seeks how much light did ray bring.
### Types of Rays
- **Primary** rays are cast from the kamera (specifically from the pixel of the viewport) and are either parallel or come from the same place of origin.
- **Shadow** rays come from a place where a ray landed towards every light source. We can figure out if that rays sees the light source or not and from that we can calculate the shadow.
- **Secondary** are created when a primary or secondary ray lands or gets refracted, they originate in the place of landing and are more chaotic then the primary rays.
### Optimization
Ray tracing is quite a complicated and difficult process, but there are ways to optimize it:
- Secondary rays have less influence on the final image.
- Intensity of light sources decreases with cubic law.
- Lower resolution
## Radiozity
A method for global illumination of a scene. It uses spreading of energy, objects can become secondary sources of light by reflection.
### Properties
- It is based on the laws of conversation of energy, so it requires a closed scene.
- Scene must be represented polygonal models (CSG, B-rep, Wireframe models).
- It is based from a two-way distribution function BRDF. 
- Before the calculation can begin it is necessary for polygons in the scene to be divided into small flats a calculate configuration factors.
- Cannot work with see-through objects.