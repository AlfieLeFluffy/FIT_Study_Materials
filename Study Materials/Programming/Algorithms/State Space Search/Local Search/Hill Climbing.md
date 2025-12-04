---
tags:
  - IAL
  - IUS
---
An algorithm that only know to go one direction and cannot go back (retrace its steps through the [[State Space|state space]]). This can mean that if it is tasked to find the highest hill from a valley it will most likely end up on the first hilltop it finds.
## Characteristic
Characteristic for the algorithm are:
- **Not Full**
- **Not Optimal**
### Complexity
The [[Time and Space Complexity|time complexity]] of this algorithm is:
- $O(d)$
- $S(1)$
## Process
Hill Climbing renders as:
1. Selects initial state.
2. Finds the highest evaluation of its neighbours and selects the highest, until there are no new states with better evaluation.
### Pseudo-Code
1. Create vertex `Current`.
2. Save the initial state and its evaluation into `Current`.
3. Expand `Current` and evaluate its direct descendants and select the one with the best evaluation.
4. If the `Current` evaluation is better then the new evaluation then return current, otherwise continue.
5. Replace `Current` with the new state and its evaluation.
6. Return to step 3.