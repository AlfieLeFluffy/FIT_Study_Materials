---
tags:
  - UPA
aliases:
  - spatial databases
---
A spatial database is a database management system that can efficiently store, query and manipulante spatial data (such as points, lines, polygons, areas, volumes, etc.). 
## Definitions
There are several terms worth defining:
- **Spatial Data**
	- Space around us, such as streets, woods, roads, power lines, etc.
	- Spatial structure of chemicals
	- VLSI circuits
	- Space, such as planets, stars, galaxies
	- Pipes, lines
- **Virtual Spatial Data**
	- Vectors of characteristics
	- Vectors of numerical attributes
## Data Types
Basic spatial data types are:
- **Points**
	- At least 2D
	- Storage of uniform data kinds
	- Not sufficient for many application
	- Intervals define points
- **(Poly-)Lines**
	- At least 2 points in higher dimensional space
	- Variable length
	- Should describe uniform data kinds
	- Not sufficient for many applications
- **Polygons**
	- At least 3 points
	- Variable length
	- Should describe uniform data kinds
	- Not sufficient for many applications
- **Areas/Volumes**
	- At least 3 points
	- Variable length
	- Should describe uniform data kinds
	- Not sufficient for many applications
## Space Types
The two main spatial types are:
- **Continuous** are usually represented by real numbers ($\mathbb{R}$) as space coordinates usually Euclidean space. 
	- Usually, instead of true real number we use approximations of real numbers rounded down to size that will not impact the resulting use case of the spatial database.
- **Discrete** use natural numbers ($\mathbb{N}$) as space coordinates and as well usually in Euclidean space (although adjusted for natural numbers).
	- There are various approaches to working in discrete spaces, such as allowing only shapes that can be built within the space or defining conditions, which must be obeyed.
	- A way of avoid having issues with the discrete space is to make the space fine grained grid in which minimal changes do not impact the whole or other solutions that are more complicated.
## Reality Mapping
Reality mapping is the use of spatial databases to map out a chunk of real (or imaginary) space into a spatial database such as to preserve as much information as possible. During this proces it is important to cover things such as:
- **Points of Interest**
- **Power Lines and Pipes**
- **Buildings**
- **Woods, Fields, Lakes, Cities, etc.**
One important element that is also necessary to cover are **holes** within the areas.
### R-Cycle
An r-cycle is a polygon stored in a discrete space representation. Such polygon is composed by a sequence of $n$ line segments $s_{1},s_{2},\dots s_{n}$ and for each line segments, it must hold that an endpoint of the line segment $s_{n}$ is equal to the starting point of the line segment $s_{n+1 \text{ mod } n}$. Importantly no line segment can intersect.
There are several states in which r-cycles can be in, such as:
- **area-nested**
- **edge-nested**
- **vertex/completely-nested**
- **area-disjointed**
- **edge-disjointed**
- **vertex/completely-disjointed**
### R-Area
An R-area $f$ is a tuple $(c,H)$, such that $c$ is an *R-cycle* and $H=\{ h_{1},\dots h_{m} \}$ is a set of R-cycles, where:
- $\forall i\in \{ 1,\dots m \}: h_{i}$ is edge-nested in c.
- $\forall i,j\in \{ 1,\dots m \},i\not=j: h_{i},h_{j}$ are edge-disjointed.
- It is not possible to create any other cycle from the segments describing $f$. This condition is an unambiguous representation of area.
### Region
A region $F$ is a set of edge-disjointed R-areas.
### Issues
This system is well-defined, but it is not sufficient as there are many issues such as overlapping areas, regions, layers, and so on.
## Operations
There are many operations over spatial data, such as:
- **Numerical Constants/Characteristics**
	- Length, size, volume, area, diameter, perimeter, etc.
- **Spatial Constants/Characteristics**
	- Middle, center of gravity, etc.
- **Metrics**
	- Distance, diameter for a set of elements, etc.
- **Predicates**
	- Equal, inside, intersects, neighbour of, etc.
- **Object Creation/Selection**
	- Intersection, difference, convex hull, etc.
Complexity of operations:
- Variable
- Some operations for spatial elements are worth to be computed during storage
Presence of operations:
- Variable
- Complex operations usually missing
Possible problems:
- Operations over sets of data
- Complex operations
- Operations are not closed over data types
### Relational Algebra
Not only algebra, but also calculus, [[Structured Query Language|SQL]], etc.
- Operations in non-spatial data involve spatial operations.
- Spatial join, select, projections.
- Operations involving viewport.
## Storage
Storing spatial data within normal relational databases has several issues, mainly with the bigger data types, such as poly-lines, polygons, areas, R-areas, regions, etc. These data types are large, variable size, complex structures, which creates issues.
Indexing spatial data is another problem as traditional indexing method, such as hashing and b-trees are not sufficient. 
### Large Data
Spatial data can be classified as large data and as such cannot be stored within regular data, which might cause skipping during search and long read times. There are quite significant size changes within a single types.
A way to solve this is to store the fixed size information such as coordinates in one place and the variable information such which polygons are made up of which coordinates elsewhere and only store pointers to that part.
### Approximation
General way of processing data is:
- $\text{Data} \leftrightarrow \text{Internal Representation} \leftrightarrow \text{User Interface}$
Spatial data types:
- $\text{Internal Representation} \leftrightarrow \text{Approximation}$
Approximation over spatial data types:
- Approximation first
- Exploitation of pre-calculated constant function results
- Algorithms from numeric geometry
- Algorithm influenced by data storage
## Indexing
Indexing is broken down into two sections depending on how complex the stored data types is:
- **Point Indexing** usually done through trees and or hashing (grid files).
- **Area Indexing** usually done through trees.
Generally, any indexing within spatial data is done through divide and conquer style mechanics of subdividing the space into smaller sub-spaces that can be more easily navigated and indexed. This also aids in approximations as areas, can be much more quickly approximated as being parts of sub-divisions of the given space.
Space decomposition (partitions, chunks) are also an easy way to keep track of neighbours, handle irregular data distribution in space and to make a search faster. 
### Point Indexing
Indexing points can be done through **k-D Tree** and its variants:
- Adaptive k-D Tree
- Bin-Tree
- BSP Tree
- Quad Tree
The basic idea is to decompose space until threshold is reached. The decomposed store in a tree structure.
The problems with k-D trees is deleting data and that trees may not be balanced.
### Area Indexing
