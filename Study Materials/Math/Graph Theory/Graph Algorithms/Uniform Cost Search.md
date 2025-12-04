---
tags:
  - IAL
  - IUS
aliases:
  - uniform cost search
  - uniform cost algorithm
  - UCS
---
A version of the [[Dijkstra Algorithm]] that uses a [[Queue|priority queue]], where the only vertexes (states) that are saved are the ones that have been reached.
## Characteristic
Characteristic for the algorithm are:
- **Full**
- **Optimal**
- Not optimal for [[Task|tasks]], where the target solution (state) lies on not many paths with high cost.
### Complexity
The [[Time and Space Complexity|time and space complexity]] for the algorithm when **b is factor of branching**, **C\* is cost of the optimal solution** and **ΔCmin is the minimal increment between two vertexes** is:
- $O(b^{C^* \times ΔCmin})$
## Process
The UCS renders as:
1. Starting vertex is pushed onto the priority queue.
2. If the priority queue is not empty then render the vertex with the lowest cost. Rendering a vertex means checking for target value and then pushing all of  its immediate descendants onto the priority queue with their evaluation, removing duplicates with higher evaluation and then pushing the current vertex onto another priority queue for finished vertexes.
### Pseudo-Code
1. Create a priority queues `OPEN` and `CLOSED`.
2. Insert the initial vertex (state) into `OPEN`.
3. If `OPEN` is empty then end the search as there is no solution, otherwise continue.
4. Take the vertex from `OPEN` with the lowest evaluation.
5. If the current vertex is the target vertex end the search as success and return the path to it, otherwise continue.
6. Expand the vertex and add all of its child vertexes into `OPEN` that are not in `CLOSED`.
7. Add the current vertex into `CLOSED`.
8. Removed duplicates in `OPEN` by selecting the lowest evaluated ones.
9. Return to step 3.