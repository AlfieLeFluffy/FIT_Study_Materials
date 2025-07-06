Is a [[Finite Automata]] that is expanded with a **pushdown stack**. For every [[Context-Free Language]] there exists a Pushdown Automata that can accept that language. **Pushdown Automata** are a seven-tuple **M = (Q, Σ, Γ, R, s, S, F)**, where:
- **Q** is a **set of states**.
- **Σ** is an **input accepted** [[Alphabet]].
- **Γ** is an **stack accepted** [[Alphabet]].
- **R** is a set of rules formatted as: **Apa ->wq** where **A ∈  Γ**, **p,q ∈ Q**, **a ∈ Σ ∪ { ε }** and **w ∈ Γ\***
- **s** is the **starting state**.
- **S** is the **starting state of the stack**.
- **F** is a **set of terminal states**.
Interpretation of the rules **Apa ->wq ∈ R** is that **p** is the current state, **a** is the current input symbol, **A** is the current symbol at the top of the stack, and so for **Apa** we can go into state **q** that will change the top of the stack from **A** to **w**, where **w** can be any combination of accepted symbols for the stack.
To visualize this we can use the same notation as for [[Finite Automata]], but updated with a new transition notation such as:
![[Stack_Automata_Diagram]]
## Types of Accepted Languages
A [[Language]] is accepted by this type of automata if either:
- **Transition into a Terminal State**
- **Emptying of the Stack**
- **Transition into a Terminal State and Emptying the Stack**
Each one of these machine types are **equivalent** and there **exists algorithms** to transforms onto into another.
## Configuration
By configuration we mean a string **χ ∈ Γ\*QΣ\*** that signifies the current state of the pushdown machine. It can be read as the full current state of the stack, the current state and the full input string.
## Deterministic Pushdown Automata (DPA)
Can move from one **configuration** to another only through one rule. This means that for every rule its left side must be unique. Pushdown State Machine is a subset of [[Finite Automata]] and a PSM cannot accept a language that a PA accepts.
## Expanded Pushdown Automata (EPA)
This is Pushdown State Machine that **can read the entire string stored on the stack**. This means that rules can include multiple symbols from the stack on their left side. Pushdown automata and expanded pushdown automata are equivalent and expanded pushdown automata.
## EPA and PA for Modeling of Syntactic Analysis
Both EPA and PA can simulate constructions of a derivation tree for a [[Context-Free Language#Context-free Grammar|Context-Free Grammar]]. We can use two approaches for this:
- **Top-Down** starts with a non-terminal and ends with a string of terminals.
- **Down-Up** starts with a string of terminals and ends with a non-terminal.
### Top-Down
To convert a CFG into a EPA for a top down analysis we need to convert the grammar elements into machine elements. The rules can be changed as:
- For each **a ∈ Σ** create a rule **asa -> s**.
- For each **A -> x ∈ P** create a rule **As -> ys** where **y** is **reverse(x)**.
- There is no final state.
### Down-Up
To convert a CFG into a EPA for a down up analysis we need to convert the grammar elements into machine elements. The rules can be changed as:
- There must be an element **\#** that is on the bottom of the stack.
- For each **a ∈ Σ** create a rule **sa -> as**.
- For each **A -> x ∈ P** create a rule **xs -> As**.
- Add a rule **\#Ss -> f**.
- There must be a final state **f** that bring all together.
