**Reinforced Learning** is different from [[Learning with a Teacher]] in that the evaluation of the actions is based on **penalization** and **rewarding** of correct and wrong end states and on the evaluations of previous walks gained from experience.
## Algorithms
### Policy-Only Learning
The princip of this algorithm is based on that in **each node of a graph** there are at **max 2 ways** (edges). Each node contains a **box with stones** of two colours: **white** and **black** (each corresponds to one way and their ration realizes probability of choosing one outcome). At the beginning of the algorithm each node has the same amount of both stones (and enough of them). Learning then comes from doing random walks through the graph (space) and if the end of the walk is:
- **Correct state** then deposite a stone into each node based on which way the walk went through. The probability of choosing this way increases.
- **Ends outside of the correct state** then from each node a corresponding stone is removed. The probability of choosing this way decreases.
After finishing learning the system chooses the way only based on the number stones in each node. In other words it does not go through with probability but only pure static conditions. This method can be expanded with more ways using more stone colours.
#### Issues
The method can have two main issues:
- In case of a general graph this method can return into previous nodes and theoretically it can trap itself in an infinite loop.
- Each action during the random walks has the same weight, even through the correct evaluations can be different.
### TD Learning (On-Policy)
A method that is based on **random walks**, during which it evaluates each states **s**, in which case state **s** is the direct predecessor of state **s'**. This causes distribution of rewards and penalizations between states. For this TD learning uses:
$$
evaluation(s) = evaluation(s) + a \times (reward(s') + b \times evaluation(s') - evaluation(s))
$$
Where:
- **a** is a coefficient of learning.
- **b** is a coefficient of the influence of next states on the evaluation of this one.
- **reward()** is a possible reward or punishment for reaching the next state.
- **evaluation()** is the evaluation of the state.
For transition between states we can use:
- Probability of transition between each state is **equal** (random policy).
- Probability of transition between each state is **different**.
- Probability of transition of one state is 1 and the others is 0 (greedy policy).
- Combination of previous transitions where it switches between random and greedy policy based on parametrem ϵ (ϵ-greedy policy).
#### Steps
1. Choose values for coefficients **a** and **b** and zero all evaluations of all states. Also zero a counter of walks and set the maximum number of walks. Set a start state **s**. 
2. Generate a new state **s'** based on the policy.
3. Evaluate the transition.
4. If the **s'** is an end state then increment the number of walks and set the state to the start state, otherwise **s'** is the new **s**.
5. If the number of walks is smaller then the maximum number of walks then return to step 2 otherwise end learning.

### Q Learning (Off-Policy)
Method of **TD Learning** that instead of state uses actions in these states and for this it uses:  
$$
Q(s,a) = Q(s,a) + a \times (reward(s') + b \times maxQ(s',a') - Q(s,a))
$$
Where:
- **a** is a coefficient of learning.
- **b** is a coefficient of the influence of next states on the evaluation of this one.
- **reward()** is a possible reward or punishment for reaching the next state.
- **Q(s, a)** signifies evaluation of **action a** made in **state s**.
- **maxQ(s', a')** signifies the **maximum** value from the evaluation of all **a'** actions that can **state s'** can make.
The method is an active method, meaning it does not have a policy (strategy) for selecting **s'**.
#### Steps
1. Choose values for coefficients **a** and **b** and zero all evaluations of **actions** of all **states**. Also zero a counter of walks and set the maximum number of walks. Set a start state **s**. 
2. Select **action a** that will lead to transition from **s** to **s'**.
3. Evaluate a new value for **action a** in **state s**.
4. If **state s'** is an end state then increment the counter of walks and return to the starting state, otherwise **s'** is the new **s**.
5. If the number of walks is smaller then the maximum number of walks then return to step 2 otherwise end learning.
### SARSA (On-Policy)
A method that combines the approaches of both **TD Learning** and **Q learning** using some strategy. 