---
tags:
  - IAL
  - IUS
aliases:
  - backtracking search
  - backtracking algorithm
  - BTS
---
Backtracking is similar to [[Depth First Search|DFS]], but instead of expansion of all vertexes (states) of the current vertex it only generates a single vertex descendant and then if returning into the current vertex generates the rest.
## Characteristic
Characteristic for the algorithm are:
- **Full**
- **Not Optimal**
- Uses a [[Stack|stack]].
- Method is suitable for **CSP**.
### Complexity
The [[Time and Space Complexity|time and space complexity]] for the algorithm when **b is factor of branching**, **m is the amount of different states** is:
- Without modification: $O( \infty)$
- With modification: $O(b^m)$ and $S(m)$.
## Process
The UCS renders as:
1. Starting vertex is pushed onto the priority queue.
2. If the priority queue is not empty then render the vertex with the lowest cost. Rendering a vertex means checking for target value and then pushing all of  its immediate descendants onto the priority queue with their evaluation, removing duplicates with higher evaluation and then pushing the current vertex onto another priority queue for finished vertexes.
### Pseudo-Code
1. Create a stack `OPEN`.
2. Insert the initial vertex (state) into `OPEN`.
3. If `OPEN` is empty then end the search as there is no solution, otherwise continue.
4. If for the top vertex in the stack a operator can be applied, then uses this operator and go to step 5. If not then remove the vertex from the stack and go to step 2.
5. If the generated vertex is the target vertex then return a success and its path, otherwise push the vertex onto the stack. A possible modification is to push the vertex onto the stack only if it is not already in the stack. Return to step 3.