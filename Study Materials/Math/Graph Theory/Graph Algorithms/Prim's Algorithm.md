---
tags:
  - IDM
aliases:
  - Prim's
---
Like [[Kruskal's Algorithm]], this algorithm is searching for the **minimal skeleton of the [[Weighted Graph|weighted graph]]**, also known as the **minimum spanning tree**. As [[Memory|memory]] it commonly uses [[Queue|priority queue]] for the unvisited vertexes.
## Process
1. Setup:
	1. Store all vertexes into memory evaluated as infinity.
	2. Choose any vertex within the [[Graph|graph]] and change its evaluation to 0.
2. In unvisited vertexes, which can be reached from the current vertex update their evaluation by the edge weight if the current evaluation is lower then the evaluation of the unvisited vertex.
3. Choose a vertex from memory, which has the lowest evaluation and remove it from memory.
4. If the memory is not empty return to the step 2.
5. Retroactively reconstruct the minimum spanning tree from the used edges.