---
tags:
  - IAL
  - IUS
aliases:
  - bidirectional search
  - bidirectional algorithm
  - BDS
---
A method that uses that can only be used for [[Task|tasks]] with reversible operators like Loyd's Eight. The algorithm starts in the initial and target vertexes (states) and works towards each other.
## Characteristic
Characteristic for the algorithm are:
- **Full**
- **Optimal**
### Complexity
The [[Time and Space Complexity|time and space complexity]] for the algorithm when **b is factor of branching**, **d is the depth of the target vertex** is:
- $O(2 \times b^{d/2})$, which is $O(b^{d/2})$
