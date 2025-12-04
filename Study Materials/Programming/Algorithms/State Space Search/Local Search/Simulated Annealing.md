---
tags:
  - IAL
  - IUS
---
An algorithm that works both with evaluation and [[Basic Probability|probability]]. As opposite to [[Hill Climbing]], this algorithm can get out of [[Extremes|local extremes]]. The method is inspired by cooling of heated metal, which means that with a lowering probability allows for selection of the worse evaluated states. At the beginning of the algorithm it is highly probable to leave local extremes. 
## Characteristic
Characteristic for the algorithm are:
- **Not Full**
- **Not Optimal**
### Complexity
The [[Time and Space Complexity|time complexity]] of this algorithm is:
- Time complexity highly depends on how quickly the temperature falls.
- $S(1)$
## Process
Hill Climbing renders as:
1. Expands the current state.
2. Select one random descendant and calculate the difference in evaluation.
3. If the difference is negative replace the current state, otherwise do it only with a probability dictated by the current temperature.
4. Increment the step and return to 1.
### Pseudo-Code
1. Create a table for lowering temperature based on the step of the rendering.
2. Create working vertex `Current`.
3. Save the initial state and its evaluation to `Current`.
4. Set the step of the rendering to 0: `k=0`.
5. Get the current temperature from the table based on the current step of rendering. If the temperature is 0 then end the search, otherwise continue.
6. Expand `Current`, select randomly one of its descendants as `Next`.
7. Calculate the difference of evaluation `ΔE` between `Current` and `Next`.
8. If `ΔE` is bigger then 0 then replace `Current` with `Next`, otherwise replace them with the probability $p=e^{ΔE/T}$.
9. Increment `k` and return to step 5.