---
tags:
  - IDM
  - IAL
  - IUS
aliases:
  - breath first search
  - BFS
---
Algorithm gradually searches through entire layers from the beginning vertex. This means the algorithm first searches through all vertexes that are on the same layer (distance from the starting vertex) before moving onto the next layer that is one unit more distant from the starting vertex.
![[Graphs_Algorithm_BFS.excalidraw.svg]]
## Characteristic
Characteristic for the algorithm are:
- **Full**
- **Optimal**
- This algorithm usually uses a [[Queue|queue]].
### Complexity
The [[Time and Space Complexity|time and space complexity]] for the algorithm when **b is factor of branching** and **d is the depth of the target vertex** is:
- Without the CLOSED variant: $O(b^{(d+1)})$
- With the CLOSED variant: $O(b^d)$
## Process
The BFS renders as:
1. Starting vertex is inserted into the queue.
2. If the queue is not empty then it renders the first vertex in the queue. Rendering a vertex means checking it for the searched value and adding its immediate descendants into the queue.
### Pseudo-Code
1. Create a queue `OPEN` and a list `CLOSED` if using the closed extended variant.
2. Insert the starting vertex (state) into `OPEN`.
3. If `OPEN` is empty then end the search as there is no solution, otherwise continue.
4. Take the top vertex from `OPEN`.
5. If the current vertex is the target vertex end the search as success and return the path to it, otherwise continue.
6. Expand the vertex and add all of its child vertexes into `OPEN` if they are not already in `OPEN` or `CLOSE`.
7. Return to step 3.
## Uses
This algorithm can be used to find the shortest distance between two vertexes of a [[Graph#Continuity|continuous]] non-weighted [[Graph|graph]].