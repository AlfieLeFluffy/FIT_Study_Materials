---
tags:
  - IFJ
  - TIN
aliases:
  - SA
---
A [[Finite Automata]] that is expanded with a **pushdown stack memory**. For every [[Context-Free Language]] there exists a **Stack Automata** that can accept that language. 
## Definition
**Stack Automata** are a seven-tuple $M = (Q, Σ, Γ, R, s, S, F)$, where:
- $Q$ is a **set of states**.
- $Σ$ is an **input accepted** [[Alphabet]].
- $Γ$ is an **stack accepted** [[Alphabet]].
- $R$ is a set of rules formatted as: $Apa \to wq$ where $A \in \Gamma$, $p,q \in Q$, $a \in \Sigma \cup \{ \epsilon \}$ and $w \in \Gamma^*$
- $s$ is the **starting state**.
- $S$ is the **starting state of the stack**.
- $F$ is a **set of terminal states**.
Interpretation of the rules $Apa \to wq \in R$ is that $p$ is the current state, $a$ is the current input symbol, $A$ is the current symbol at the top of the stack, and so for $Apa$ we can go into state $q$ that will change the top of the stack from $A$ to $w$, where $w$ can be any combination of accepted symbols for the stack.
To visualize this we can use the same notation as for [[Finite Automata]], but updated with a new transition notation such as:
![[Stack_Automata_Diagram.excalidraw.svg]]
## Acceptation Types
A [[Formal Language]] is accepted by this type of automata if either:
- **Transition into a Terminal State**
- **Emptying of the Stack**
- **Transition into a Terminal State and Emptying the Stack**
Each one of these machine types are **equivalent** and there **exists algorithms** to transforms onto into another.
## Configuration
By configuration we mean a string $X \in QΣ^*Γ^*$ that signifies the current state of the pushdown automata. It can be read as the the current state, the current rest of the input string and full current state of the stack.
### Defintion
For a stack automata $P = (Q, Σ, Γ, R, s, S, F)$ a configuration of $P$ is a three-tuple $(q,w,\alpha)$, where:
- $q$ is the current state of the automata.
- $w$ is the remaining unprocessed part of the input string.
- $\alpha$ is the current contents of the stack in sequential order with the first symbol being the top of the stack.
### Transition
A transition between configurations in SA is a [[Relation#Binary Relation|binary relation]] $\vdash_{P}$ defined over a [[set]] of configurations as:
$$(q,w,\beta)\vdash_{P}(q',w',\beta') \Leftrightarrow w =aw' \wedge \beta = Z\alpha \wedge \beta'=\gamma\alpha \wedge(q', \gamma) \in \sigma(q,a,Z)$$
where:
- $q,q' \in Q$
- $a \in \Sigma \cup\{\epsilon\}$
- $w,w' \in \Sigma^*$
- $Z \in \Gamma$
- $\alpha,\beta,\beta' \in \Gamma^*$
Some properties of these transitions are:
- If $a=\epsilon$, then we call this transition and $\epsilon$-transition.
- Relations $\vdash_{P}^i,\vdash_{P}^*,\vdash_{P}^+$ are defined same as in [[Finite Automata]].
- If it applies that for string $w \in \Sigma^*$ relation $(q_{0},w_{0},Z_{0})\vdash_{P}^*(q,\epsilon,\gamma)$, where $q \in F$ and $\gamma \in \Gamma^*$, then we can say that $w$ is accepted by stack automata $P$ and the two configurations are the beginning and end configurations respectively.
- A definition of a [[Formal Language|language]] being accepted by a stack automata $P$ is $L(P) = \{ w|(q_{0},w_{0},Z_{0})\vdash_{P}^* (q,\epsilon,\gamma) \wedge q\in F\}$.
## Types
Apart from the basic type of stack automata there are also two other types:
### Deterministic Pushdown Automata
![[Deterministic Stack Automata]]
### Expanded Pushdown Automata
![[Expanded Stack Automata]]
## Usecases
One common use case of stack automata in computer science is in [[Syntactic Analysis Modeling]], which is checking if a syntax of a program is correct.
