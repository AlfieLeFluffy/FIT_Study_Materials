---
tags:
  - FLP
aliases:
  - lambda-calculus
sources:
  - "[[FLP_00_Merged_2024.pdf]]"
---
Lambda-calculus is a mathematical model of [[Functional Programming|Functional Languages]], meaning all FL can be converted into lambda-calculus without exception.
## Syntax
The basic syntax of lambda-calculus is:
```
expression -> variable
			(expression expression)
			(\ variable.expression)
```
### Variable
Signifies *any possible value* and can use either **typed** or **type-less** approach. There is also a difference between **bound** and **free** variables:
- $\lambda f.(f \ x)$
	- $x$ is in $(f \ x)$ free
	- $f$ is in $(f \ x)$ bound
## Characteristics
Some basic characteristics of lambda-calculus are:
- **Application** $(e_{1} \ e_{2})$
	- Represents application of function $e_{1}$ on expression $e_{2}$.
	- The result can still be applicable.
- **Abstraction** $(\lambda x.e)$
	- Represents function with parameter $x$ and body $e$.
- **Substitution** $e_{1}[e_{2}/x]$
	- Substitution of expression $e_{2}$ for every free occurrences of variable $x$ in expression $e_{1}$. 
- **Correct Substitution** $e_{1}[e_{2}/x]$
	- Any *free* variable in $e_{2}$ cannot become *bound*.
- **alpha-Conversion**
	- Renaming of variables
		- $(\lambda x.e) \leftrightarrow (\lambda x'.e)[x'/x]$
		- The substitution must be correct.
	- Using
		- Unification
		- Better readability of expressions
- **beta-Conversion**
	- Evaluation of abstraction
		- $(\lambda x.e_{1})e_{2} \leftrightarrow e_{1}[e_{2}/x]$
		- The substitution must be correct.
	- Operational symbol
		- Changes the form of the expression, but not its value.
		- Global strategy for evaluation (sequence).
- **gamma-Conversion**