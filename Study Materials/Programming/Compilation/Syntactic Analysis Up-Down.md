---
tags:
  - IFJ
---
Syntactic analysis from down-up used in in [[Compiler|compilers]] is based on [[Context-Free Grammar#Derivation Direction|LL Grammars]] and LL tables. LL grammars without ε rules is [[Context-Free Grammar|CFG]] = (N, T, P, S), where for each **t, A** it is valid that **t ∈ T**, **A ∈ N** and there exist only one rule **A -> X1X2...Xn ∈ P** such that **t ∈ First(X1X2...Xn)**. LL grammars with ε rules will remove left recursions, but also require other functions/sets **Empty**, **Follow**, **Predict**.
## Auxiliary Functions
### First(x)
A [[Set|set]] of all terminal symbols by which a derivable [[String|string]] **zx, x ∈ (N∪T)*** can begin.
### Empty(x)
A [[Set|set]] of only one symbols ε if x derivates ε, otherwise the set is empty.
### Follow(A)
A [[Set|set]] of all terminal symbols, that can occur to the right of A within the sentence form, where A is non-terminal symbol.
### Predict(A -> x)
A [[Set|set]] of all terminal symbols, that can be generated leftmost if for any sentence form we use the rule A->x.
## Implementation of LL Analysis
There are two main ways of implementing of up-down analysis.
### Recursive Descent
Each non-terminal symbol is represented by a procedure/function, that renders its syntactic analysis and can recursively call procedures/functions of other non-terminal symbols as per rules.
	An example of this could be rule **E -> TF**, for which can be called the procedure for handling **E**, which would call a procedure for **T** and then if the previous T procedure was successful would call procedure for **F**, which if also successful would resolve E procedure as also successful. 
### Predictive Syntactic Analysis
This type uses a syntactic analyser with a [[Stack|stack]] and a **LL table**. The right side of the rules are being stored in the stack in a reverse order (**reversal**) and renders the syntactic analysis of the non-terminal symbol on the top of the stack.
	For example for each non-terminal symbol can be defined a field of procedures/functions, which render the rule during loading of a symbol. If the symbol does not have a procedure/function then it results in an error.