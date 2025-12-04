---
tags:
  - IAL
  - IUS
aliases:
  - min-conflict search
  - minimal conflict search
  - min-conflict algorithm
  - MCS
---
An search algorithm for finding the optimal assignment of values to a set of variables (states), with minimal conflicts.
## Characteristic
Characteristic for the algorithm are:
- There is no [[Formal Proof|formal proof]] that this algorithm is full or optimal.
- Uses a [[Stack|stack]].
- Method is suitable for **CSP**.
### Complexity
There is no [[Formal Proof|formal proof]] for [[Time and Space Complexity|time complexity]] of this algorithm, but space complexity is $S(1)$.
## Process
The MCS renders as:
1. Select for each variable $x_{i}(i=1,\dots, n)$ a random value from a [[Set|set]] of available values.
2. Set the auxiliary variable **i** (counter of variables) and **j** (counter of correctly assigned values) to 1.
3. Count the *amount of possible conflicts* for each value of variables $x_{i}$.
4. If for each different value $x_{i}$ exists a amount of conflicts lower or same as their current value, then change the value to this value and set **j** to 1, otherwise increment **j**.
5. If $j==n$ (all variables are assigned the best way possible), then the optimal solution was reached, otherwise increment **i** and continue.
6. If value $i>n$, then $i=1$ and return to step 2.