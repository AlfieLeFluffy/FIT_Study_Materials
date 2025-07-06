A finite [[Automata]] is an ordered five-tuple **M = {Q, Σ, R, s, F}**, where:
- **Q** is the **finites set of states**.
-  **Σ** is the **input** [[Alphabet]].
- **R** is a **finite set of rules** in the shape: **pa -> q** where **p ∈ Q**and **q ∈ Q** and **a ∈ Q ∪ {ε}**
- **s ∈ Q** and is the **starting state**.
- **F ⊆ Q** and is the **set of terminal states**.
Graphically we can visualize them as:
![[Automata_Diagram]]
## Accepted Language
If by **any string of input symbols** the automata gets into a **final state** of the machine then we say that the [[Language]] **is accepted**.
## Equivalent Finite Automata
Two models for formal languages (for example final state machines) are equivalent if they specify that **same** [[Language]].
## Types
- **Non-determinable** can include **ε** transitions (rules) and there exist states in which by the **same symbol** we can move into **multiple states**.
- **Without Epsilon Transitions** does not contain **ε** transitions (rules).
- **Determinable** cannot include **ε** transitions (rules) and in each state a symbol can only result in one outcome state.
- **Fully Determinable** is determinable and for each symbol of the alphabet there exist exactly one transition in each state.
- **Well Specified** does not contain **any unreachable states** and has only **one non-terminal state**. For each final state machine there exists one Well Specified final state machine.
- **Minimal** contains only distinguishable states. For well specified machines there exists exactly one Minimal machine.
## Determinization of Automata
Transformation of non-deterministic automata into a deterministic one. If a non-deterministic FSM has **n states** then the deterministic one has **2<sup>n</sup> states**. Each non-deterministic NFM has its deterministic variant.
### Steps
1. Removing of all **ε transitions** using a **ε closure**. It is a set of all states that we can achieve by reading any symbol.
2. From the original state we create new states that are a set of states into which we can go into by an overflow of any symbol. If any new states contain a terminal state then we signify that state as also terminal.
3. We repeat step 2. until there are no more states that can be combined.
