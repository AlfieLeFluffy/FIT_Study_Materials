---
tags:
  - FLP
aliases:
  - lambda-calculus
sources:
  - "[[FLP_00_Merged_2024.pdf]]"
  - "[[FLP_01_Lambda_Calculus.pdf]]"
---
Lambda-calculus is a mathematical model of [[Functional Programming|Functional Languages]], meaning all FL can be converted into lambda-calculus without exception.
## Syntax
The basic syntax of lambda-calculus is:
```
expression -> variable
			(expression expression)
			(\variable . expression)
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
## Derivations
- **alpha-Derivation**
	- Renaming of variables
		- $(\lambda x.e) \leftrightarrow (\lambda x'.e)[x'/x]$
		- The substitution must be correct.
	- Using
		- Unification
		- Better readability of expressions
- **beta-Derivation**
	- Evaluation of abstraction
		- $(\lambda x.e_{1})e_{2} \leftrightarrow e_{1}[e_{2}/x]$
		- The substitution must be correct.
	- Operational symbol
		- Changes the form of the expression, but not its value.
		- Global strategy for evaluation (sequence).
- **gamma-Derivation**
	- Ignoring of empty free variables
		- $(\lambda x.e_{1}x) \leftrightarrow e_{1}$
## Fixed Point
A fixed point in mathematics is a point for which a function return the same value as is the input. A fixed points of the function $f(x) = x^2$ are technically $\{ 0,1 \}$, because if we insert them into function then we get them back. In lambda-calculus we can use this for *recursion* and *bottom*.
The basic idea is:
- The fixed point operator: `Y`
- The fixed point of `E` is: `YE`
- For `E` the fixed point is: `k = YE`
- From the definition we get: `E k = k = YE = E(YE)`
## Recursion
Using the fixed point operator, we can create recursion as: `YE = E (YE)`. Combined with an if statement means we can end the recursion, giving us such expressions as:
```
LET ?: = λ x y z . x y z 
LET LTfn = λ f x y . (iszero y) ? False : ((iszero x) ? True : (f (prev x) (prev y))) 
LET LT = Y LTfn
```
The above functions check if the first number is less then the second number (both recursive). If none of the ending criteria are met then the function delves deeper. This is done by passing the function into a fixed point operator. A quick explanation of the derivation can be:
```
LT 5 6
Y LTfn 5 6
LTfn (Y LTfn) 5 6
Y LTfn 4 5
...
```
