---
tags:
  - IAL
  - IUS
aliases:
  - Problem Solving
  - problem solving
---
State space search or problem solving is solving of a [[Task|task]] (problem) through searching inside of a [[State Space|state space]]. For this we use commonly known algorithms described below.
## Algorithm Characteristics
There are several characteristics by which we can divide problem solving algorithms which are:
### Evaluation Criteria
- **Fullness** refers to when an algorithm always find a solution, if the [[Task|task]] has a solution. Each full algorithm that is **CSP** (Constraint Satisfaction Problem, where finding the target state is the only relevant factor) is also **optimized**. 
- **Optimization** refers to when there are multiple solutions, the algorithm finds the best one. Not all optimized algorithms have to be full.
- [[Time and Space Complexity]]
### Algorithm Types
- **Blind (Non-informed)** algorithms do not use any information, that would make it easier to find a solution to a task. These algorithms are only used when there is truly no information that would help solve the task.
- **Informed** algorithms use some information through **heuristic** functions about the task that aid the algorithm or make it solvable.
- **Local Search** algorithms only searches around the current state instead of systematic searching of the state space. These algorithms are useful for optimization tasks (problems) and do not have to be full or optimal. 
## Terms
- **State Expansion** means evaluation (determination) of all immediate follow-up states (states connected through edges) of the current state.
- **State Evaluation** is given by a sum of the [[Weighted Graph|weights]] (costs) of the edges from the root state to the target state.
## Blind Algorithms
As mentioned above, blind algorithms do not use any information that could help the algorithm to find a quicker solution. These algorithms commonly are the same or rather similar to [[Graph Algorithms|graph algorithms]] and include:
### Breath Firsts Search
![[Breath First Search]]
### Depth First Search
![[Depth First Search]]
### Depth Limited Search
![[Depth Limited Search]]
### Iterative Deepening Search
![[Iterative Deepening Search]]
### Bidirectional Search
![[Bidirectional Search]]
### Uniform Cost Search
![[Uniform Cost Search]]
### Backtracking Search
![[Backtracking Search]]
### Forward Checking Search
![[Forward Checking Search]]
### Min-Conflict Search
![[Min-Conflict Search]]
## Informed Algorithms
Search algorithms that use [[Math Function|functions]] (heuristics) for **cost estimation of a path** from the current state to the goal (target) and add them to the **path cost** of the current state. The function **f(S<sub>k</sub>)** is the evaluation of the **k-th** state, which is given by sum of:
- **g(S<sub>k</sub>)** is the cost of the path from the initial state to the k-th state.
- **h(S<sub>k</sub>)** is the cost estimation of the path from the k-th state to the goal (target) state.
### Best First Search
![[Best First Search]]
### Greedy Search
![[Greedy Search]]
### A* Search
![[AStar Search]]
## Local Search Algorithms
Local search algorithms usually are not **full** or **optimal**, but can be for example rather fast.
### Hill Climbing
![[Hill Climbing]]
### Simulated Annealing
![[Simulated Annealing]]