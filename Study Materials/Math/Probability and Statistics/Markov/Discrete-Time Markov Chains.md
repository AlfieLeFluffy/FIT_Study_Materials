---
tags:
  - MSP
aliases:
  - discrete-time markov chains
  - DTMC
  - DTMCs
---
Discrete-Time [[Markov Chain]] is one possible [[Markov Chain#Probabilistic Models|probabilistic model]] that works within discrete time (there is a set minimal time step) and are fully probabilistic (all of their decisions are made based on probabilities).
## DTMC Definition
Formally, a Discrete-Time Markov chain is a three-tuple **(S, s0, P)** where:
- **S** is a **finite set of states**, also known as [[State Space]].
- **s<sub>0</sub> ∈ S** that is the **initial state**.
- **P : S x S -> \[0 , 1\]** is the **transition probability matrix**, where **∀s ∈ S: sum<sub>s'∈S</sub>( P(s,s') ) = 1**.
![[Markov_Chain_Example.excalidraw.svg|350]]
### Transition Probability Matrix
A matrix **P** that is a (right) stochastic matrix, where rows of P are sum of 1.
 $$
P =
\begin{pmatrix}
0 & 0.9 & 0.1 \\
0.5 & 0.5 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
The matrix describes the probability of one state changing into another. Can be thought of as a table.
## Memorylessness
Also know as **Markov property** and it means that the probability of transition from one state into another only depends on the current state and ignores all previous states, is independent of the past.
## Transient Analysis
An analysis of Markov chains over time after starting at s<sub>0</sub>. One such analysis is **transient probability**, which results in a [[Vector]] containing the probability of the system ending up in a state in time **k >= 0**. 
$$t_{k}(s) = P(X(k) = s | X(0) =s_{0})$$
Calculating this through brute force methods is possible (calculating each possible step one by one), but these calculations would be expensive. Instead it is possible to apply the **Markov property** directly. 
$$ t_{k}(s) = \sum_{s'∈ S}t_{k-1}(s') * P(s',s); where t_{0}(s_{0})=1$$
This means starting with the initial vector in time 0 and state s<sub>0</sub> and then propagate it by multiplying it with the **probability matrix**.
### Example
Given the Markov chain example from before:
![[Markov_Chain_Example.excalidraw.svg|350]]
and its probability matrix:
 $$
P =
\begin{pmatrix}
0 & 0.9 & 0.1 \\
0.5 & 0.5 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
we can calculate each possible state in the transient analysis in linear time as:
$$t_{0} = (1,0,0)$$
$$t_{1} = t_{0} * P = (0,0.9,0.1)$$
$$t_{2} = t_{1} * P = (0.45,0.45,0.1)$$
$$t_{3} = t_{2} * P = (0.225,0.63,0.145)$$
This way it possible to calculate the probability of ending up in each state by the end time **k** without the need of exploring all possible options.
## Reachability
To figure out the probability of reaching a state **t ∈ T**, assuming a non-empty set **T ⊆ S** of target states, we can use a linear system:
$$x(s) = 1\text{;} \ \text{if} \ s ∈ T$$
$$x(s) = \sum_{s'∈ S}P(s,s')*x(s')\text{;}  \ \text{if} \ s \ not∈ T$$
#### Example
Using the Markov chain example from above:
![[Markov_Chain_Example.excalidraw.svg|350]]
And the the target state set is $T={error}$:
$$x(\text{error}) = 1$$
$$x(\text{start}) = 0.9\times x(\text{error})+0.1\times x(\text{delivered})$$
$$x(\text{delivered}) = 1 \times x(\text{delivered})$$
$$x = (0.9+0.1\times p,1,p)$$
### S<sub>0</sub> States
S<sub>0</sub> are such states that $S_{0} = [ s \varepsilon S|\text{T is not reachable from s} ]$
#### Example
Taken the previous example, but introducing $S_{0}$ states we get:
$$x(\text{error}) = 1$$
$$x(\text{delivered}) = 0$$
$$x(\text{start}) = 0.9\times x(\text{error})+0.1\times x(\text{delivered})= 0.9\times_{1}+0.1\times_{0}=0.9$$
$$x = (0.9,1,0)$$
## Expected Time to Reach
An expected time to reach a set of target states **t ∈ T** can be done in a similar fashion to figuring out if they can be reached.
$$e(s) = 0 \ ; \ \text{if s ∈ T}$$
$$e(s) = 1 + \sum_{s'∈S}P(s,s')\times e(s') \ ; \ \text{if s not ∈ T}$$
These two equations mean that:
- An expected time to reach a terminal node from a terminal node **is 0** as it has already been reached.
- Time to reach a terminal node from a non-terminal node is **at least 1** and the sum of the expected time of upcoming nodes times the probability of reaching the node.
#### Example
Given DTMC:
![[Markov_Chain_Example.excalidraw.svg|350]]
Looking expected time to reach $delivered$:
$$e(delivered) = 0$$
$$e(error) = 1 + 0.5 \times e(start) + 0.5 \times e(error)$$
$$e(start) = 1 + 0.9\times e(error)+0.1\times e(delivered)$$
$$e(start) = 28$$
## Limiting Distribution
Limiting distribution describes what would happen if a transient analysis and its transient probability distribution $t_{k}$ would evolve over a long time and approach infinite steps. 
$$t_{\infty}(s) = \lim_{ k \to \infty } t_{k}(s) = \lim_{ k \to \infty } P(X(k) = s| X(0) = s_{0})$$
If there exists a limit as described above then we can say that $t_{\infty}$ represents the limiting distribution. This distribution can also be calculated by enough steps of classic transient analysis where the increments made in a new steps are rounded out.
## Classification of States
There are two possible classifications a state can be in:
- **Recurrent** state is such state that upon leaving it, it is always possible to return to back into it.
	- Once a recurrent state is visited they are visited infinitely often.
	- States reachable from a recurrent state form a **recurrent** class. In [[Graph|graph]] theory recurrent classes are bottom strongly connected component (BSCC).
- **Transient** states are non-recurrent states that are eventually abandoned forever and it is not possible to always return to them.
![[Markov_Chain_Classification.excalidraw.svg|350]]
If a markov chain has only a single recurrent class, then the [[Markov Chain#Limiting Distribution|limiting distribution]] is independent of the initial state.
### Periodicity
Recurrent class is periodic if its states can be group into **cyclic classes** such that transitions from one class lead to the next one. This means that if at least one state contains a self-loop, the class is aperiodic.
![[Markov_Chain_Periodicity.excalidraw.svg|350]]
### Aperiodic Theorem
A markov chain with aperiodic recurrent classes has a [[Markov Chain#Limiting Distribution|limiting distribution]].
## Steady State Theorem
In a chain with a single aperiodic recurrent class, the limiting distribution is independent of the initial state and coincides with the **steady-state (stationary) distribution π** satisfying:
- System of balance equations: $\forall s: \pi(s)=\sum_{s'}\pi(s')\times P(s',s)$
- Normalization condition: $\sum_{s}\pi_{s}=1$ or if using the matrix notation: $\pi=\pi \times P,1^T\pi=1$
### Properties
- $\pi(s)=0$ for each transient state **s**.
- Stationary distribution **π** always exists, even if the limiting does not, for example for the following periodic chain with $\pi=(0.5,0.5)$.
![[Markov_Chain_Stationary_Distribution_Example.excalidraw.svg]]

---
### Sources
- [[MSP_01_Introduction_and_Makrov_chain.pdf]]