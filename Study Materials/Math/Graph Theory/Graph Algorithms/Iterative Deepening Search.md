---
tags:
  - IAL
  - IUS
aliases:
  - iterative deepening seach
  - iterative deepening algorithm
  - IDS
---
An algorithm using [[Depth Limited Search|DLS]] to search the [[State Space|state space]] through an iterative method.
## Characteristic
Characteristic for the algorithm are:
- **Full**
- **Optimal**
### Complexity
The [[Time and Space Complexity|time and space complexity]] for the algorithm when **b is factor of branching**, **d is the maximum searched depth** is:
- $O(b \times d)$
- $S(b^d)$
## Process
The IDS renders as:
1. Sets the maximum depths to **x**.
2. Uses [[Depth Limited Search|DLS]] with **x**, which if not successful increments **x** and returns to step 1.
### Pseudo-Code
1. Set max depth to 1.
2. Call [[Depth Limited Search|DLS]] for max depth.
3. If [[Depth Limited Search|DLS]] ends in success then return as success and the path.
4. If [[Depth Limited Search|DLS]] ends in failure and *there was at least one vertex (state) not explored*, increment the max depth and return to step 2.