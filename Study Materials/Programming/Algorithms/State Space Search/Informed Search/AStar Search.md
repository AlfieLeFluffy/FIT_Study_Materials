---
tags:
  - IAL
  - IUS
aliases:
  - a* search
  - A*
---
A* algorithm is a [[Best First Search|BestFS]] version that uses a heuristic function where the value is the **lowest estimation of the real cost** to the target state. This function can never over-evaluated the estimation, otherwise the algorithm won't work correctly. An value of **h=0** can be acceptable, but then the method is just [[Uniform Cost Search|UCS]].
## Characteristic
Characteristic for the algorithm are:
- **Full**
- **Optimal**
### Complexity
The [[Time and Space Complexity|time and space complexity]] for GS when **b is the factor of branching** and **d is the depth** is:
- For **h** close to 0: $O(b^d)$
- For **h** equal to the real value: $O(d)$