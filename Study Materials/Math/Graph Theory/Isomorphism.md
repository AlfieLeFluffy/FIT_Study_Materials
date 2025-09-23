---
tags:
  - IDM
aliases:
  - isomorphism
  - isomorph
---
Isomorphism of [[Graph|graphs]] **G** and **H** is a [[View#Bijective (Shared Unique) View|bijective view]] of **f: V(G) -> V(H)**, where each pair **u, v ∈ V(G)** is connected though an edge only if there exists a pair **f(u), f(v) ∈ V(G)** that are connected through an edge in graph **H**. In another notation:
$$ \exists F: F(G) \to V(H): (x,y) \in E(G) \Leftrightarrow (f(x),f(y)) \in E(H)$$
For isomorph graphs **G** and **H** it applies that:
- **G** and **H** have the same amount of vertexes.
- **G** and **H** have the same amount of edges.
- [[View]] **f** always connects vertexes of the same degree.
## Checking for Isomorphism
1. Check if both graphs have the same amount of vertexes.
2. Check if both graphs have the same amount of edges.
3. Create an ordered list of vertexes for both graphs by the vertex degree and check if both list are the same.
4. Check all possible approaches to isomorphism view.
![[Graphs_Examples_Definition_Isomorphism.excalidraw.svg]]