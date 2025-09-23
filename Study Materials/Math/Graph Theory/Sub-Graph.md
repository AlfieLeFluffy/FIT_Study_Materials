---
tags:
  - IDM
aliases:
  - sub-graph
  - subgraph
  - Subgraph
---
Sub-graphs of [[Graph|graph]] **G** can be understood as any [[Graph|graph]] **H** for that applies:
- A [[Set|set]] of vertexes of graph **H** that is a [[Set#Subset|subset]] of vertexes of graph **G**: **V(H) ⊆ V(G)**.
- A [[Set|set]] of edges, which is any [[Set#Subset|subset]] of the [[Set|set]] edges of graph G where both of the vertexes are part of **V(H)**.
![[Graphs_Examples_Definition_Subgraph.excalidraw.svg]]
## Inducted Sub-Graph
A sub-graph **H ⊆ G** such that it contains all edges of graph **G** between pairs of vertexes from **V(H)**. Otherwise said it is a graph containing all edges between vertexes of the original excluding those of removed vertexes.
![[Graphs_Examples_Definition_Inducted_Subgraph.excalidraw.svg]]
## Types of Subgraphs
Most of the subgraphs found in other graphs can have the same types as [[Graph Types|graphs types]]. Some special cases are:
- **Inducted circle** is an [[Sub-Graph#Inducted Sub-Graph|inducted subgraph]] that is [[Isomorphism|isomorph]] to some circle.
- **Clique** is a subgraph that is [[Isomorphism|isomorph]] to some full graph.
- **Independent [[Set|set]]** is a subset of vertexes that does not have any edges between them.