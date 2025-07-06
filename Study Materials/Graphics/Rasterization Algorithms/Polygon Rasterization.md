To rasterize the borders of a polygon we can just use [[Line Rasterization]] algorithms, but to colour in a polygon we need more complex solutions.
## Types
We have two main types of polygons:
- **Convex** polygons, where any two given points of this polygon, a line between these points is part of the polygon's area (the line is inside the polygon).
- **Concave** polygon, where the given rule for convex polygons does not apply (there can be an area where if we connect two points the line does not have to be part of the polygon).
We can also have different types of polygon fill:
- **Solid colour**
- **Hatch**
- **Texture**
- **Gradient**
## Scanline Fill
It is a basic algorithm for filling in a general polygon. The input for the method is a list of oriented points (peaks) and the output is a rasterized polygon.
### Princip
- Searches for the **maximum** and **minimum** values of **X** and **Y** and frames the area in which the polygon resides.
- The area is walked through line by line.
- The algorithm calculates intersections with edges of the polygon and if the the number of intersections (in a current pixel) are odd then the pixel gets coloured in.
### Evaluation
The algorithm has issues with **local extremes** and **horizontal lines**.
- **Horizontal lines** are skipped over as there is no good way of handling them.
- **Local extremes** can be fixed in by shortening the **Y axis** from each side by 1 pixel or that both intersections in a pixel are counted.
## Inverse Scanline Fill
This version does not require testing for edges on each line of the polygon. The input for the method is a list of oriented points (peaks) and the output is a rasterized polygon.
### Princip
- Searches for the **maximum** and **minimum** values of **X** and **Y** and frames the area in which the polygon resides.
- For each edge find coordinates for its **Y<sub>min</sub>** and  **Y<sub>max</sub>**.
- For each edge find lines that intersect this edge and **pixel to the right** of this intersections get inverted (blank -> coloured, coloured -> blank).
- In the end all edges need to be rasterized as well.
### Evaluation
The algorithm fixes some of the issues with the normal Scanline, but is overall more complex.
## Pined Algorithm
Works only with **Convex** polygons like triangles, which are always convex. It allows for easy realization in [[Hardware (HW)]]. The area is described by the list of edges.
### Princip
- The area gets divided into two halves, one for positive and one for negative for each edge. This is usually done through a function to which when we would add the coordinates of a pixel it would return either a positive or a negative number.
- Coloured in are all pixel that are in the positive areas of all edges. If all the edge functions return a positive number for a given point.
### Edge Function - E<sub>i</sub>(x, y)
For the edge function we can use vectors for the edge and a vector for the tested point:
```
hi = (x1 - x0, y1 -y0) # edge vector 
bpi = (x - x0, y - y0) # point vector
E(x, y) = hi * bpi
E(x, y) = (x- xi0)Δyi - (y -yi0)Δxi
```
## Seed Fill
The area that should be filled in need to be defined by a continuous border made of pixel of the desired area (the edges need to be drawn ahead). 
### Princip
- A seed gets placed into the area, which spread to neighbouring points (colouring them in).
- Coloured point become seeds themselves and so in recursion the entire polygon gets filled in. We can remove the recursion by instead using a queue.
- To find the neighbouring points we can commonly use either a **4-sided** or a **8-sided** mask, but the 8-sided mask has an issue where it can escape the area through angled edges. 
