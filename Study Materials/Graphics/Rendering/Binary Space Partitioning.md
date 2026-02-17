---
tags:
  - PGR
aliases:
  - BSP
  - binary space paritioning
sources:
  - "[[PGR_03_Global_Visibility.pdf]]"
---
This method involves dividing the scene in halves until all objects are inside the tree. The convention is that the scene is first divided vertically, then the half are divided horizontally, and their halves vertically and so on recursively. This can be done through BSP trees that can be:
- Axis-aligned
- Poligon-aligned
These trees are not flexible enough for dynamic rendering of scenes as the computation of BSP trees can take too long.
Another way of dividing the space is by using each node as a division of the space into two by a plane. This is mainly used in polygon aligned BSP trees and one helpful property is that if the scene is walked through from the back to the front the rasterization then can use the painter's algorithm without using a Z-Buffer. Each node can also store information about visibility of each object.