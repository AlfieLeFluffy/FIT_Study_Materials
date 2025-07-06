Propositional logic is based on a formal deductive systems from syntactic and deduction rules.
## Syntax
Syntax is given by an **alphabet** and **grammar**, like in [[Language]]s.
- **Alphabet** is an infinite set of propositional symbols (variables), logic symbols or conjunctions (**¬, ∧, ∨, →, ↔**) and logical constants (**0 and 1**). Such an alphabet can look like **X = {¬, ∧, ∨, →, ↔, (, ), 0, 1, x, y, z, ...}**
- **Grammar** are rules how these alphabet symbols are supposed to be stringed together. **Beware** that propositional logic does not take create logic without individual **precedence of the logic symbols**.
	- If **x** is a propositional variable **x ∈ X** then **x**, **0** and **1** are formulas.
	- If **ϕ** and **ψ** are formulas then even **(¬ϕ), (ϕ ∧ ψ), (ϕ ∨ ψ), (ϕ → ψ), (ϕ ↔ ψ)** are formulas.
	- **Formulas** of the propositional logic are all finite strings generated using the previous two rules.
	
## Semantic
Sematic gives each formula its **meaning** and defines what **truth value** will a formula result in each evaluation. This value is commonly defined using a truth table. A truth table resolve the truth value of formulas **ϕ** and **ψ** on each of the formulas value (resolves for all possibilities). 

| ϕ   | ψ   | ¬ϕ  | ϕ ∧ ψ | ϕ ∨ ψ | (ϕ → ψ) | (ϕ ↔ ψ) |
| --- | --- | --- | ----- | ----- | ------- | ------- |
| 0   | 0   | 1   | 0     | 0     | 1       | 1       |
| 0   | 1   | 1   | 0     | 1     | 1       | 0       |
| 1   | 0   | 0   | 0     | 1     | 0       | 0       |
| 1   | 1   | 0   | 1     | 1     | 1       | 1       |
## Properties
-  **I |= ϕ** - **I** fulfils **ϕ** if based on its evaluation of variables **I** of formula **ϕ** the evaluation is **1** then the model **I** fulfils the formula.
-  **I \/|= ϕ** - **I** does not fulfils **ϕ** if based on its evaluation of variables **I** of formula **ϕ** the evaluation is **0** then the model **I** fulfils the formula.
- A formula is **fulfillable** if at least for one model of evaluation the formula is fulfilled.
- A formula is **not fulfillable** it is not fulfillable.
- A formula is **valid** (**|= ϕ, tautologia**) if for all models of evaluation the final value is **1**.
- A formula is **not valid** (**\/|= ϕ**) if for all models of evaluation the final value is **0**.
## Logical Equivalence and Logical Consequence
- **Logical Equivalence** is when for two formulas **ϕ** and **ψ** all of their evaluations for variables **I** that **I** is the model for both formulas. This is notated as  **ϕ ⇔ ψ**.  
- **Logical Consequence**: Formula **ψ** is the logical consequence of **ϕ** when for every evaluation of variables **I** the model is fulfils for **ϕ** and **I** is then a model of **ψ** as well. This is notated as  **ϕ ⇒ ψ**. 
Do not misunderstand these symbols for implication and biconditional from above. Those are used inside of formulas and these once are used to compare formulas. 
## Normal Forms
Normal forms are formulas that fit some specific syntactic notation.

![[Negation Normal Form (NNF)]]

![[Product of Sums (CNF)]]

![[Sum of Products (DNF)]]
