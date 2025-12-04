---
tags:
  - IAL
  - IUS
aliases:
  - best first search
  - BFS
  - BestFS
---
An **non-informed** search [[Uniform Cost Search|UCS]] is the worst case example of BestFS, for which h(S<sub>k</sub>) is always 0.
## Characteristic
Characteristic for the algorithm are:
- Uses a [[List|list]].
## Process
The BFS renders as by selecting a state with the lowest evaluation from a list and then expanding it.
### Pseudo-Code
1. Create a list `OPEN` (and `CLOSED`).
2. Append initial state with its evaluation to `OPEN`.
3. If `OPEN` is empty then the [[Task|task]] has no solution and return failure, otherwise continue.
4. Select a state from `OPEN` with the best evaluation.
5. If the current state is the target state then end in success and return the path, otherwise continue.
6. Expand the current state. 
	1. Append all of its descendants with their evaluations that are not its predecessors (if not using `CLOSED`).
	2. Remove duplicates of states in `OPEN` with worse evaluations.
	3. Return to step 3.