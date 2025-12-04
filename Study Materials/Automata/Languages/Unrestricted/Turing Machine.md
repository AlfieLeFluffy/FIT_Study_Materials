---
tags:
  - ITU
  - to_be_finished
aliases:
  - TM
  - Turing machine
---
Turing machines are the most unrestricted and most powerful of the machines/automate from the [[Chomsky Hierarchy]].
## Church-Turing Theses
The Cherch-Turing theses roughly is:
	"*Turing machines (and their equivalent system) defines its computational power to what we can intuitively consider as effectively calculable.*"
## Definition
A **Turing machine** (TM) is an ordered six-tuple $M=(Q,\Sigma,\Gamma,\sigma,q_{0},q_{f})$, where:
- $Q$ is a [[Set|finite set]] of of internal (controlling) states.
- $\Sigma$ si the [[Alphabet|alphabet]], where $\Delta \not\in \Sigma$.
- $\Gamma$ is a [[Set|finite set]] of symbols that is the tape [[Alphabet|alphabet]], where $\Sigma \subset \Gamma, \Delta \in \Gamma$
- $\sigma$ is the transitional function $\sigma: (Q \setminus \{ q_{f} \}) \times \Gamma \to (\Gamma \cup \{ L,R \}$, where $L,R \not\in \Gamma$.
- $q_{0} \in Q$ is the initial state.
- $q_{f} \in Q$ is the final state.
## Configuration
A configuration of Turing machine is defined by the current control state and configuration of the tape or tapes. Formally it is an element from a [[Set|set]] $Q\times \{ \gamma \Delta^w|\gamma \in \Gamma^* \} \times \mathbb{N}$.
### Tape Configuration
Configuration of a tape is a tuple made of an infinite string representing the contents of the tape and position of the reading head over this string. Formally it is an element from a [[Set|set]] $\{  \gamma \Delta^w|\gamma \in \Gamma^* \} \times \mathbb{N}$. 
A specific configuration of the tape is written as $\Delta xyzz\Delta \underline{x} \Delta \Delta\dots$, where the underlined symbol is the position of the head. 
The symbol $\Delta$ signifies an empty cell (place) within the tape.
### Transition
A **transition step** in **Turing machine** $M$ is defined as the **smallest** [[Relation#Binary Relation|binary relation]] $\vdash_{M}$ such that $\forall q_{1},q_{2} \in Q \forall \gamma \in \Gamma^w \forall n\in \mathbb{N} \forall b \in \Gamma$:
- Operation of **moving right**
$$(q_{1},\gamma,n)\vdash_{M}(q_{2},\gamma,n+1) \ \ \text{for} \ \ \sigma(q_{1},\gamma_{n})=(q_{2},R)$$
- Operation of **moving left**
$$(q_{1},\gamma,n)\vdash_{M}(q_{2},\gamma,n-1) \ \ \text{for} \ \ \sigma(q_{1},\gamma_{n})=(q_{2},L)\wedge n>0$$
- Operation of **writing underneath the head**
$$(q_{1},\gamma,n) \vdash_{M} (q_{2},s^n_{b}(\gamma),n) \ \ \text{for} \ \ \sigma(q_{1},\gamma_{n})=(q_{2},b)$$
### Turing Machine Processing
A processing of a **Turing machine** $M$ begins in configuration $K_{0}$ and is a sequence of configurations $K_{0},K_{1},K_{2},\dots$, where:
- $K_{i} \vdash_{M}K_{i+1}$ for all $i\geq0$ such that $K_{i+1}$ is in the specific sequence.
- The sequence is either:
	- **Infinite**
	- **Finite** with a final configuration $(q,\gamma,n)$, which can one of several ways a TM stops, which are:
		- **Normal**, by transition into a final state.
		- **Abnormal**, where the TM didn't end in a final state, the TM tried to move left in the left most position or there is not defined transition in $\sigma$ for configuration $(q,\gamma_{n})$.
## Accepted Laanguages
A string $w$ is accepted by a Turing machine $M = (Q,\Sigma,\Gamma,\sigma,q_{0},q_{f})$ if $M$ during activation (simulation) from the initial configuration $\underline{\Delta}w\Delta$ and initial state $q_{0}$ stops by transition into a final state $q_{f}$.
A [[Set|set]] $L(M) = \{ w|w\ \text{is accepted by TM }M \}  \subseteq \Sigma^*$, then we can say that the language is accepted by Turing machine $M$.
Alternatively, an acceptation of string in Turing machine can be defined such that the Turing machine starts with tape configuration $\underline{\Delta}w\Delta$ and stops with tape configuration $\underline{\Delta}Y\Delta$, where $Y \in \Gamma\setminus \Sigma$ and $Y$ signifies Yes.
## Types
There are several special types of Turing machines, such as:
### Multi-Tape Turing Machine
![[Multi-Tape Turing Machine]]
### Non-Deterministic Turing Machine
![[Non-Deterministic Turing Machine]]
### Universal Turing Machine
![[Universal Turing Machine]]
### Complete Turing Machine
![[Complete Turing Machine]]
### Linearly Limited Automata
![[Linearly Limited Automata]]
## Relation with Computable Functions
Turing machines processing and functions can be defined by [[Computable Function|computable functions]] and more specifically [[Computable Function#Turing Computable Function|Turing Computable Function]].