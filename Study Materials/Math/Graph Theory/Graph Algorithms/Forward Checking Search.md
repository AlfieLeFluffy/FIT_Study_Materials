---
tags:
  - IAL
  - IUS
aliases:
  - forward checking search
  - forward checking algorithm
  - FCS
---
A searching algorithm for searching a minimal conflict solution to a [[Graph|graph]] or [[State Space|state space]], using [[Set|sets]] of possible values that a state can be evaluated as.
## Characteristic
Characteristic for the algorithm are:
- **Full**
- **Optimal**
- Uses a [[Stack|stack]].
- Method is suitable for **CSP**.
### Complexity
The [[Time and Space Complexity|time and space complexity]] for the algorithm when **n is the number of variables** and **m is the number of values** is:
- $O(m^n)$
- $S(n)$
## Process
The FCS assigns to each vertex (state) a [[Set|set]] of possible allowed values it can be evaluated for, without creating a conflict.
Main loop:
1. Assign the initial state an evaluation from the set of possible evaluations and update all neighbouring states' sets of possible evaluations to exclude the selected evaluation. 
2. Select another state and assign it an evaluation from the set and updated neighbouring states.
3. If a state's set of possible evaluations is emptied then previous evaluation have to updated. If the evaluations can no longer be changed then the [[Task|task]] has no solution.
The FCS can use several heuristics for:
- Selection of variables:
	- Variables with the lowest amount of possible values.
	- Variables which have the highest possible impact to restrict possibilities of other states.
- Selection of the variable's value:
	- Value which excludes the lowest amount of value that have shared restrictions with the selected variable.