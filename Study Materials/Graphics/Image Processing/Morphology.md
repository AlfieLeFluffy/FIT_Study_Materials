---
tags:
  - ZPO
aliases:
  - morphology
  - mathematical morphology
  - Mathematical Morphology
sources:
  - "[[ZPO_07_Mathematical_Morphology.pdf]]"
---
Morphology is the study of size, shape and internal structure of objects. In image processing it is used to extract knowledge from the relation of an image and a small structuring element of a predefined shape.
## Operations
There are two main binary operations done in morphology, which are:
- **Dilation**: expands an object/image by a predefined kernel
- **Erosion**: erodes an object/image by a predefined kernel
During these operations, each pixel is checked by the structuring element. Both of these operations can work over a *point set*, instead of a real image for simplification.
### Point Set
An image can be represented by a point [[Set|set]] of arbitrary dimension. An example of such point set can be $X=\{ (0,0),(1,1) \}$, which can be imaged as an $2\times2$ image containing two pixels diagonally (but the dimensions can be different).
### Structural Element
A structural element can be thought of as a special kernel used in binary morphology. These elements have the structure of the desired resulting pixel overlap. For example if we have a structural element which are three pixels in a horizontal row then within the image during erosion, only pixels that have two neighbors on either side will remain.
The structural elements can look like: 
$$\begin{matrix}
&& \\
1&1&1 \\
&& \\
\end{matrix}
\ \ \ ; \ \ \ \begin{matrix}
&1& \\
1&1&1 \\
&1& \\
\end{matrix}
\ \ \ ; \ \ \ \begin{matrix}
&1& \\
&1& \\
&1& \\
\end{matrix}
\ \ \ ; \ \ \ \begin{matrix}
1&& \\
&1& \\
&&1 \\
\end{matrix}$$
## Deriving Methods
Methods that use dilation and erosion to achieve some goal.
### Contour
We can extract the contour/outline of an image (point set) by dilation by an expanding structural element (makes the image bigger) and then subtracting the original image from the new image.
### Opening
Binary opening is used to remove noise/unwanted structures around an object. The process to do that is by first eroding the image by a reasonable structural element, for example $3 \times 3$ and the dilation of the result by the same kernel.
This gets rid of small image noise and objects smaller then the element.
### Closing
The idea is similar as binary opening, but instead of removing noise outside the image, this method fills in any noise inside the image. The steps within this method are the exact opposite of the ones within opening, so the first step is to do dilation with a reasonable element, such as $3 \times 3$ and then erosion of the result by the same element.
This gets rid of empty noise within an object.
### Hit or Miss Transformation
Uses a special structural element, that can be rotated, to detect four possible configuration of convex corners within an object. The 4 versions of the structural element look like $$\begin{matrix}
&1& \\
0&1&1 \\
0&0& \\
\end{matrix}
\ \ \ ; \ \ \ \begin{matrix}
&1& \\
1&1&0 \\
&0&0\\
\end{matrix}
\ \ \ ; \ \ \ \begin{matrix}
&0&0 \\
1&1&0 \\
&1&\\
\end{matrix}
\ \ \ ; \ \ \ \begin{matrix}
0&0& \\
0&1&1 \\
&1&\\
\end{matrix}$$
### Skeleton
An object skeleton is a simplified description of an object's shape. This is useful in shape recognition. A more technical name would be "Medial Axis Transformation," which is a locus of points equidistant from the contour. It can also be explained by an analogy of grass fire, where you can image the object as a patch of grass and the skeleton as the last sections of grass to burn if we set fire to the entire contour at ones.
Another technical way of defining is based on the concept of the maximal circle. 
- A circle $B(p, r)$ with center $p$ and the radius $r\geq 0$ is the [[Set|set]] of points for which distance $d\leq r$. 
- The maximum circle $B$ inscribed into the set $X$ touches its boundary in two or more points. 
This is computationally way too complex to do as it would require to check all points within an image and all possible radius length for each pixel.
Another, more simple, way to do create a skeleton is through binary operations dilation and erosion. For this we use these two structural elements: 
$$\begin{matrix}
0 & 0 & 0 \\
  & 1 &   \\
1 & 1 & 1 \\
\end{matrix}
\ \ \ ; \ \ \ \begin{matrix}
  & 0 & 0 \\
1 & 1 & 0 \\
  & 1 &   \\
\end{matrix}$$
These two elements are used to erode the image $4 \times$, each time the element is rotated by $90\degree$. Both elements ensure that the connectivity is not broken. The end condition of the algorithm can be no changes between iterations are made.
The method Hit or Miss can also be used.
### Distance Transform
Distance transformation of *point set* $A$ assigns to each point $p \in X$ value, which is its distance from the background. A two-pass algorithm is used (top-down, bottom-up). All points within the image are initialized either to $\infty$ when a background or $0$ when part of the object. The forward pass uses this element:
$$\begin{matrix}
0 & 1 \\
1 & s \\
\end{matrix}$$
The backward pass uses this element:
$$\begin{matrix}
0 & 1 \\
1 & s \\
\end{matrix}$$
### Grayscale Morphology
Grayscale mathematical morphology is a generalization of the binary morphology for images with more gray levels then two. The point set is $A \in E^3$, where the first two components represent the 2D image coordinates and the third component corresponds to the image value.
The structural element is a function of two variables. It influences how pixels in the neighborhood of the current pixel are taken into account.