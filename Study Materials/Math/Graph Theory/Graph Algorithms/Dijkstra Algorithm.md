---
tags:
  - IDM
aliases:
  - Dijkstra
---
An algorithm for searching the **shortest path** (distance) between two vertexes in a positively [[Weighted Graph|weighted graph]]. As its [[Memory|memory]] it uses a [[Queue|priority queue]]. It can have a [[Time and Space Complexity| time complexity]] of $O((\text{edges}+\text{vertexes})\times \log(\text{vertexes}))$ or $O(\text{vertexes}^2)$ if an [[Array|array field]] is used instead.
## Process
1. Setup:
	1. All vertexes with the exception of the starting vertex are valued as infinity. 
	2. Starting vertex is valued as 0. 
	3. All vertexes are flagged as unfinished.
2. From unfinished vertexes choose such that it has the smallest evaluation (meaning it is at the beginning of the queue) and:
	1. If the vertex is the target vertex then end the algorithm and go to step 4.
	2. If the vertex is not the target vertex then re-evaluate all vertex which the current vertex can reach by adding together the current evaluation of the current vertex and the weight of the edge towards the vertex and checking if the resulting number is lower then the evaluation that the vertex already has.
3. Currently rendered vertex is flagged as finished and if there are unfinished vertexes we return to step 2.
4. Retroactively reconstruct the path from the target vertex to the starting vertex based on the stored values from point 2.