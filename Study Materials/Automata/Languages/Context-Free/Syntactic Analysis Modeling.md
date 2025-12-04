---
tags:
  - IFJ
aliases:
  - syntactic analysis modeling
  - modeling of syntactic analysis
---
Both [[Expanded Stack Automata|ESA]] and [[Stack Automata|SA]] can simulate constructions of a derivation tree for a [[Context-Free Language#Context-free Grammar|Context-Free Grammar]]. We can use two approaches for this:
- **Top-Down** starts with a non-terminal and ends with a string of terminals.
- **Down-Up** starts with a string of terminals and ends with a non-terminal.
### Top-Down
To convert a CFG into a EPA for a top down analysis we need to convert the grammar elements into machine elements. The rules can be changed as:
- For each $a \in \Sigma$ create a rule $a/a \to s$.
- For each $A \to x \in P$ create a rule $A / \epsilon \to y / \epsilon$ where $y$ is $reverse(x)$.
- There is no final state.
### Down-Up
To convert a CFG into a EPA for a down up analysis we need to convert the grammar elements into machine elements. The rules can be changed as:
- There must be an element $\#$ that is on the bottom of the stack.
- For each $a \in \Sigma$ create a rule $\epsilon/ a \to a /\epsilon$.
- For each $A \to x \in P$ create a rule $x /\epsilon \to A /\epsilon$.
- Add a rule $\#S/\epsilon \to f$.
- There must be a final state $f$ that bring all together.