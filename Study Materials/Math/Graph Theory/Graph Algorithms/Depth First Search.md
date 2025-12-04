---
tags:
  - IDM
  - IAL
  - IUS
aliases:
  - depth first search
  - DFS
---
Algorithm first moves into the most distant layer and then gradually goes closer and then deeper into the graph until it searches through all vertexes.
![[Graphs_Algorithm_DFS.excalidraw.svg]]
## Characteristic
Characteristic for the algorithm are:
- **Not Full** (with CLOSED modification it is **full**)
- **Not Optimal**
- This algorithm usually uses a [[Stack|stack]].
### Complexity
The [[Time and Space Complexity|time and space complexity]] for the algorithm when **b is factor of branching**, **d is the depth of the target vertex** and **m is the number of different vertexes** is:
- Without the CLOSED variant: $O(\infty)$ 
- With the CLOSED variant: $O(b^m), S(m)$
- With the CLOSED variant for [[Tree|tree]]: $O(b \times d)$
## Process
The DFS renders as:
1. Starting vertex is pushed onto the stack.
2. If the stack is not empty then render the top vertex in the stack. Rendering a vertex means checking for target value and then pushing all of  its immediate descendants onto the stack.
### Pseudo-Code
1. Create a stack `OPEN` and a list `CLOSED` if using the closed extended variant.
2. Insert the starting vertex (state) into `OPEN`.
3. If `OPEN` is empty then end the search as there is no solution, otherwise continue.
4. Take the top vertex from `OPEN`.
5. If the current vertex is the target vertex end the search as success and return the path to it, otherwise continue.
6. Expand the vertex and add all of its child vertexes into `OPEN` if they are not already in `OPEN` or `CLOSE`.
7. Return to step 3.
