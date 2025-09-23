---
tags:
  - IDM
aliases:
  - breath first search
  - BFS
---
Algorithm gradually searches through entire layers from the beginning vertex. This means the algorithm first searches through all vertexes that are on the same layer (distance from the starting vertex) before moving onto the next layer that is one unit more distant from the starting vertex. This algorithm usually uses a [[Queue|queue]].
![[Graphs_Algorithm_BFS.excalidraw.svg]]
## Process
The BFS renders as:
1. Starting vertex is inserted into the queue.
2. If the queue is not empty then it renders the first vertex in the queue. Rendering a vertex means checking it for the searched value and adding its immediate descendants into the queue.
## Uses
This algorithm can be used to find the shortest distance between two vertexes of a [[Graph#Continuity|continuous]] non-weighted [[Graph|graph]].