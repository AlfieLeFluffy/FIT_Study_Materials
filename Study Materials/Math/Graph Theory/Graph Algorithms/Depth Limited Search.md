---
tags:
  - IAL
  - IUS
aliases:
  - depth limited search
  - depth limited algorithm
  - DLS
---
A version of the [[Depth First Search|DFS]] that searches only to a certain depth from the starting vertex (state).
## Characteristic
Characteristic for the algorithm are:
- **Not Full**
- **Not Optimal**
- This algorithm usually uses a [[Stack|stack]].
### Complexity
The [[Time and Space Complexity|time and space complexity]] for the algorithm when **b is factor of branching**, **i is the searched depth** is:
- $O(b \times i)$
- $S(b^i)$
## Process
The DLS renders as:
1. Starting vertex is pushed onto the stack.
2. If the stack is not empty then render the top vertex in the stack. Rendering a vertex means checking for target value and then pushing all of  its immediate descendants onto the stack, unless those descendants are deeper then the max searched depth.
### Pseudo-Code
1. Create a stack `OPEN`.
2. Insert the starting vertex (state) into `OPEN`.
3. If `OPEN` is empty then end the search as there is no solution, otherwise continue.
4. Take the top vertex from `OPEN`.
5. If the current vertex is the target vertex end the search as success and return the path to it, otherwise continue.
6. If the depth of the current vertex (state) is lower then the maximum searched depth then expand the vertex and add all of its child vertexes into `OPEN`.
7. Return to step 3.