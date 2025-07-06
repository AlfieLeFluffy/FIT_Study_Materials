Unlike in [[Propositional Logic]], Predicate Logic offers much richer expressive (communication) tools. It is once again comprised from an **alphabet** and a **grammar**:
- **Alphabet** is comprised of:
	1. **Logical Conjunctions** (Operations): ¬, ∧, ∨, →, ↔
	2. **Variables**: x, y, z, ... ∈ X, where X is a continuous infinite set of variables.
	3. **Quantifiers**: ∃, ∀
	4. **Parenthesis**: (, )
	5. **Function Symbols**: f<sub>1</sub>, f<sub>2</sub>, ... ∈ F (+<sub>/2</sub>, sin<sub>/1</sub>, e<sub>/0</sub>)
	6. **Predicate Symbols**: p1, p2, ... (<<sub>/2</sub>)
	7. **Predicate Symbol of Equivalence**: =<sub>/2</sub>
	Function and predicate symbols have **arity**, signifying with how many parameters ([[Operand]]s) they work.
- **Grammar** has two main structures:
	1. **Terms** 
		1. If **x** is a variable (**x ∈ X**) then a string "**x**" is a term.
		2. If **f** is a function symbol with arity **n** a **t1, ..., tn** are terms then string "**f(t1, ..., tn)**" is a term.
	2. **Formulas**
		1. If **p** predicate symbol with arity **n** a **t1, ..., tn** are terms then string "**p(t1, ..., tn)**" is a formula. This also applies for the embedded binary predicate symbol **=**. We call a formula for this form an **atomic formula**.
		2. If there are **formulas** **ϕ** and **ψ**, then formulas are also strings **"(¬ϕ)", "(ϕ ∧ ψ)", "(ϕ ∨ ψ)", "(ϕ → ψ)", "(ϕ ↔ ψ)"** .
		3. If there is a formula **ϕ** and a variable **x ∈ X** then formulas are also **"(∃xϕ), (∀xϕ)"**
## Syntax
Syntax of predicate logic is made up of the **alphabet** and **grammar**. Function and predicate symbols also are not **fixed** in their placement in the syntax, meaning we can think of them as **parameters** of the language, that we choose depending on what exactly do we want to convey. It is a signature property of a predicate logic language that is given as a double of **<set of function symbols, set of predicate symbols>**. This means that we can have predicate logic languages such as:
- Language of ordering with signature \<F = ∅ P = {<=<sub>/2</sub>}\> :
	- ∀x ( x <= x )
	- ∀x∀y ( (x <= y  ∧ y <= x) → x = y)
- Language of ordering with signature \<F = {\*<sub>/2</sub>, e<sub>/2</sub>} P = {<=<sub>/2</sub>}\> :
	- ∀x ( x * e = x ∧ x * e = x)
	- ∀x∀y( x * y = e ∧ x * y = e)
### Variable Restrictions
There are two types of variables restrictions:
#### Bound Variables
An occurrence of a variable in a formule is bound, if there is in a range of applicability of one of the predicate symbols. If a variable is bound, then it is bound to the nearest predicate symbol above itself. An example of where both variables are bound is:
```
∀x ( ∃y( f(x) = y))
```
Where as in the next one the first appearance of **x** in **p(x)** is free as there is no predicate symbol restricting it:
```
p(x) ∧ ∀x ( ∃y( f(x) = y))
```
#### Free Variables
As in the example above, free variables are not about by a predicate symbol. A variable is **free** if **at least one of its appearances if free**. Formulas with free variables are called **propositional form** while once without a free variable are called a **closed formule** or a **statement**.
## Semantic
A semantic of the predicate logic is more complicated then with [[Propositional Logic]]. In predicate logic we must assign variables value from some universum (natural, whole, real numbers) and we must interpret each function and predicate symbol. This can also be called **realization of the language**. For example to evaluate the formule bellow we must:
```
∀x( f(x) < y)
```
1. Find the value of variable **y**.
2. What is the universum in which **∀x** works.
3. What is the sematic of the function symbol **f()**.
4. What is the semantic of the predicate symbol **<**.