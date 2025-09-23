---
tags:
  - IDM
aliases:
  - Kruskal's
---
Like [[Prim's Algorithm]], this algorithm is searching for the **minimal skeleton of the [[Weighted Graph|weighted graph]]**, also known as the **minimum spanning tree**. 
## Process
The main princip that inside the [[Graph|graph]] we always choose the edge with the lowest weight, but that would not create a loop (is not already in the minimum spanning tree). We choose these edges until all vertexes are connected to the minimum spanning tree.