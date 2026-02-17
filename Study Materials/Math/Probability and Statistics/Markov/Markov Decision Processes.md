---
tags:
  - MSP
  - to_be_finished
aliases:
  - markov decision processes
  - MDP
sources:
  - "[[MSP_02_Markov_Decision_Processes.pdf]]"
---
Markov Decision Processes are **non-deterministic discrete-time** [[Markov Chain#Probabilistic Models|probabilistic model]] and are the **non-deterministic** counterpart of the **fully probabilistic** [[Discrete-Time Markov Chains]] (DTMCs).
## Advantages
Unlike [[Discrete-Time Markov Chains|DTMCs]] we can model certain behaviours that former cannot, such as:
- Some systems aspects or decisions should not be modelled probabilistically:
	- **Concurrency** or scheduling of parallel components
	- Unknown model parameters
	- Unknown environment or adversary
- To model controllable probabilistic systems:
	- **Control theory** of which MDPs essentially are.
	- Performing an action leads to a probability distribution over its outcome.
	- Many application domains such as operational research, motion planning, optimal control.
- Close connection between MDPs and [[Reinforcement Learning|reinforcement learning]] problems:
	- Scheduling in probabilistic environment, motion planning, etc.
## Princip
As mentioned above MDPs are an extensions of [[Discrete-Time Markov Chains|DTMCs]] which allow for non-deterministic choice in combination with probabilities.
## MDP Definition
Formally, a Markov Decision Process is a four-tuple **(S, s<sub>0</sub>, Act, P)**, where:
- **S** is a finite [[Set|set]] of states or [[State Space]].
- **s<sub>0</sub> ∈ S** is the initial state.
- **Act** is a finite [[Set|set]] of actions:
	- $\text{Act}(s) ⊆ Act$ denotes the [[Set|set]] of actions available at state $s \in S$.
	- We assume $\forall s: \text{Act}(s)\not= \emptyset$, which means no deadlocks.
- **P: S x Act x S -> \[0,1\]** is the **transition probability matrix** where for all **s ∈ S** and **α ∈ Act** holds $\sum_{s'\in S}P(s,\alpha,s') = 1$ if **α** is available in $s(\alpha \in \text{Act}(s))$, and otherwise $P(s,\alpha,s')$ represents the probability of transitioning from **s** to **s'** when executing action **α**.
## MDP Paths
A **finite path** within MDPs is a sequence of states and actions: $\pi=s_{0}\alpha_{0}, s_{1}\alpha_{1},s_{2}\alpha_{2},\dots, s_{n}$, where $\alpha_{i} \in \text{Act}(s_{i})$ and $P(s_{i},\alpha_{i},s_{i+1})>0$. It represents a concrete **execution** of the MDP, which resolves both types of *choices*. Some additional notation is:
- $\text{last}(\pi)=s_{n}$ denotes the last state of path $\pi$.
- $\text{Paths}_{m}$ denotes the [[Set|set]] of finite paths in $M$.
## Scheduler
Scheduler, otherwise known as *controller*, *policy*, *strategy* or *adversary*, **resolves** the **non-deterministic choices**. Scheduler $\sigma:\text{Paths}_{M}\to\text{Distr}(\text{Act})$ assigns to every finite path $\pi$ a probability distribution $\sigma(\pi)\in\text{Distr(Act)}$ over actions $\text{supp}(\sigma(\pi)) \subseteq\text{Act}(\text{last}(\pi))$.
### Types
There are several types of schedulers, of which some are:
- **Deterministic** scheduler assigns to a path a single action: $\sigma:\text{Paths}_{M}\to\text{Act}$.
- **Memoryless** scheduler picks action based only on the current state: $\sigma:S\to\text{Distr(Act)}$.
- **Deterministic Memoryless** scheduler: $\sigma:S\to Act$.
### Induced DTMC
Scheduler $\sigma$ for [[Markov Decision Processes|MDP]] $M=(S,s_{0},\text{Act},P)$ induces [[Discrete-Time Markov Chains|DTMC]] $M^\sigma=(\text{Paths}^M,s_{0},P^\sigma)$ where $P^\sigma(\pi,\pi'):=\sigma(\pi)(\alpha)\times P(\text{last}(\pi),\alpha)(s')$ if $\pi'=\pi \alpha s'$, and 0 otherwise. This means that a MDP can be induced into a DTMC, which means that the decisions that would be left to the scheduler are turned into probabilistic choices. For example if the scheduler had to options $\alpha,\beta$, then we can say that the probabilities were $\frac{1}{2}, \frac{1}{2}$.
For a **deterministic memoryless scheduler** $\sigma$ the induced [[Discrete-Time Markov Chains|DTMC]] is defined as $M^\sigma=(S,s_{0},P^\sigma)$ where $P^\sigma(s,s')=P(s,\sigma(s),s')$.
# Model Checking MDPs
We can use the same specification language as for [[Discrete-Time Markov Chains|DTMCs]].
### Verification vs Synthesis
- **Verification** checks if **all schedulers** satisfy the specifications.
- **Synthesis** find **a scheduler** that satisfies the specification or prove that it does not exist.
## Enumerating
### Key Idea
The key idea of model checking is to compute the minimum $P_{\text{min}}(s_{0}\to T)$ or the maximum $P_{\text{max}}(s_{0}\to T)$ reachability probabilities over all schedulers.
This corresponds to the analysis of the **best-** or **worst-case** behaviour of the MDP. To compute the min/max probabilities, it is sufficient to only consider *deterministic memoryless schedulers*, which is not true for all specifications, but is sufficient for reachability.
#### Disadvantages
Enumerating all memoryless schedulers is not tractable. The computational complexity is $O(|\text{Act}^{|S|}|)$ for all memoryless schedulers. There are more advanced techniques that have a much better efficiency such as **linear programming**, **value iteration**, policy iteration, etc.
## Linear Programming
In linear programming we can use a set of linear equations to generate constraints which maximize or minimize the outcome we seek.
### Princip
To compute $P_{\text{min}}(s\to T)$ for $\forall s\in S$:
1. Identify states with probability 1 ($S_{1}$) and 0 ($S_{0}$), which is a graph-based problem.
	1. Intuition for probability 1 is: *all paths over all schedulers lead to T*
	2. Intuition for probability 0 is: *exists a scheduler for which no path leads to T*
2. For the remaining states $S_{?} = S\setminus(S_{1} \cup S_{2})$ solve the **linear program**:
$$\text{maximise} \sum_{s\in S_{?}}x_{s}\text{ subuject to the constratints:}$$
$$x_{s}\leq \sum_{s'\in S_{?}}P(s,\alpha,s')\times x_{s'}+\sum_{s'\in S_{1}}P(s,\alpha,s')\times_{1}$$
$$0\leq x_{s}\leq_{1}$$
$$\text{for all }s\in S_{?} \text{ and for all } \alpha \in \text{Act}(s)$$

To compute $P_{\text{max}(s\to T)}$ for $\forall s\in S$: ㅤ
1. Identify states with probability 1 ($S_{1}$) and 0 ($S_{0}$), which is a graph-based problem.
	1. Intuition for probability 1 is: *exists a scheduler for which all paths lead to T*
	2. Intuition for probability 0 is: *for all schedulers there is not path leading to T*
2. For the remaining states $S_{?} = S\setminus(S_{1} \cup S_{2})$ solve the **linear program**:
$$\text{minimize} \sum_{s\in S_{?}}x_{s}\text{ subuject to the constratints:}$$
$$x_{s}\geq \sum_{s'\in S_{?}}P(s,\alpha,s')\times x_{s'}+\sum_{s'\in S_{1}}P(s,\alpha,s')\times_{1}$$
$$0\leq x_{s}\leq_{1}$$
$$\text{for all }s\in S_{?} \text{ and for all } \alpha \in \text{Act}(s)$$
## Value Iteration Approach
Value iteration approach/algorithms as their name suggest start from a initial state and with each step of calculation they get closer to the actual value to the point that new iterations do not meaningfully change the outcome.
### Princip
To calculate $P_{\text{min}}(s\to T) = \lim_{ n \to \infty } x_{s}^{(n)}$:
$$x_{s}^{(n)} =
    \begin{cases*}
        1 & {if s in T}\\
        0 & {if s in Sno or n = 0}\\
        \text{min}_{\alpha\in\text{Act}(s)}\left( \sum_{s'\in S}P(s,\alpha,s')\times x_{s'}^{(n-1)} \right) & otherwise
    \end{cases*}
$$
It is similar to calculate $P_{\text{max}}(s\to T) = \lim_{ n \to \infty } x_{s}^{(n)}$, but with the internal function swapped. To find out the optimal option to choose in each state we can look at what action was chosen in the last iteration.
### Examples
#### F/B Coin Toss
For MDP:
![[MDP_Coin_Toss_Example.excalidraw.svg|300]]
We want to calculate the maximum probability of winning, so we maximize reachability as:
$$x_{s}^{(n)} =
    \begin{cases*}
        1 & {if s in T}\\
        0 & {if s in Sno or n = 0}\\
        \text{max}_{\alpha\in\text{Act}(s)}\left( \sum_{s'\in S}P(s,\alpha,s')\times x_{s'}^{(n-1)} \right) & otherwise
    \end{cases*}
$$
So, we create the first step of the iteration as:
$$x^{(0)} = (odd, even,W,L) = (0,0,1,0)$$
Then we iterate for the first time as:
$$x^{1}(odd) = max\{ 0.5\times 1;0\} = 0.5$$
$$x^{1}(even) = max\{ 0.5\times 1;0.5\times1\} = 0.7$$
$$x^{1}(W) = 1$$
$$x^{1}(L) = 0$$
So then after the first iteration we get:
$$x^{(1)} = (odd, even,W,L) = (0.5,0.7,1,0)$$
This can be done for ever, making the result of each iteration more precise until the new changes are insignificant, such as lost in rounding or enough iteration have been reached.
