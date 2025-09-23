---
tags:
  - IDM
aliases:
  - graph
---
Informally a graph is made up of vertexes connected through edges.
## Definition
The formal definition of a graph is a tuple **G = (V, E)**, where:
- **V** or **V(G)** is a [[Set|set]] of vertexes (end points), such as **{a,b,c}**.
- **E** or **E(G)** is a [[Set|set]] of edges or a set of selected two-element subsets (tuples of binary relations) of the vertex set, such as  **{(a,b), (b,c)}**. Another notation of an edge such as **(a,b)** can be **ab**.
Vertexes connected through an edge are **neighbouring vertexes**.
### Vertex Degree
The degree of a vertex **x** of graph **G** is the sum of edges that **x** is a part of. Annotation of this operation is **d<sub>G</sub>(x)**. A graph can be **d-regular** is all vertex have the same degree. The min and max values are noted as:
- **∆(G)** the vertex with the maximum degree from the graph G.
- **δ(G)** the vertex with the minimum degree from the graph G. 
## Setup
There are two main ways of setting up a graph entity through either graphics or formal definition.
### Graphically
A graph can be setup informally through graphical means such as:
![[Graphs_Examples_Definition.excalidraw.svg]]
### Formally
The formal definitions is $G(V,E)$, $V=\{1,2,3,4\}$ and $E=\{(1,2),(1,3),(1,4),(3,4)\}$.
## Navigating Graphs
There are two main ways of *walking* through graphs:
- **Sequence** is an ordered list of vertex such that there exists an edge between each pair of vertexes in sequence. Vertexes and edges can be repeated in the sequence and can the sequence can contain loops. 
- **Stroke** is a sequence that cannot repeat vertexes or edges. A closed stroke is such stroke that ends in the vertex it starts in. A graph **G** can be drawn in one stoke if it is continuous and all vertexes have an even degree.
## Continuity
The ability to move from any vertex to any other vertex through edges. In other words for each pair of vertexes **u,v ∈ V(G)** there exists a **sequence** from vertex **u** to vertex **v**. 
### Continuity Relation
[[Relation]] **~** over [[Set|set]] of vertexes **V(G)** of any graph **G** is defined as **u,v ∈ V(G)** are in relation **u~v** if there exists a **stroke** that starts in **u** and ends in **v**. This relation is:
- [[Relation#Properties|Reflexive]]
- [[Relation#Properties|Symmetric]]
- [[Relation#Properties|Transitive]]
This means that relation **~** is relation of [[Relation#Known Binary Relations|Equivalence]].
### Continuity in Oriented Graphs
For [[Oriented Graph|oriented graphs]] we differentiate:
- **Weak continuity** is when the graphs is continuous if we remove its orientation.
- **Strong continuity** is when the graphs is continuous even through its orientation.
### Continuity Components
Components are separate classes of [[Relation#Known Binary Relations|equivalence]] of the graph and a graph is continuous if it has only one class.
![[Graphs_Examples_Definition_Continuity.excalidraw.svg]]
## Types of Graphs
![[Graph Types]]

## Oriented Graph
![[Oriented Graph]]
## Weighted Graph
![[Weighted Graph]]
## Sub-Graph
![[Sub-Graph]]
## Isomorphism
![[Isomorphism]]
## Tree
![[Tree]]