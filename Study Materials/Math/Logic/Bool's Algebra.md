Bool's algebra is an [[Relation#Algebra|algebraic]] structure that uses only binary symbols (**∧, ∨**) and an unary symbol (**¬**). It is **distributive complementary** [[View#Union (Svaz)|Union (Svaz)]]. Bool's algebra can be described as a sextuple **(B, ∧, ∨, ¬ , 0, 1)**. where:
- **B** is an non-empty [[Set]].
- **0 ∈ B** and is the smallest element.
- **1 ∈ B** and is the biggest element.
- **∧** is a **binary** operation of **intersection** (infimum).
- **∨** is a **binary** operation of **union** (supremum).
- **¬** is a **unary** operation of **complementary**.
### Switching Algebra
Another term for Bool's algebra that signifies that in this system ([[Binary System]]) we are using all operations (**AND, OR, NOT**). This is the use of Bool's algebra to do calculations in the binary system.
## Axioms
There are several axioms:
- **Closeness** (uzavřenost): (a ∨ b) ∈ B, (a, b) ∈ B
- **Identity** (identita): a ∨ 0 = a, a ∧ 1 = a
- **Commutativity** (Komutativita): a ∨ b = b ∨ a, a ∧ b = b ∧ a
- **Distributivity** (Distributivita): a ∨ (b **Agresivity of 0** c) =  (a ∨ b)∧(a ∨ c), a ∧ (b ∨ c) =  (a ∧ b)∨(a ∧ c)
- **Complementarity** (Komplementárnost): a ∧ ¬a = 0, a ∨ ¬a = 1
- There exist at least 2 elements in the set B.
## Properties
- **Agresivity of 0**: a ∧ 0 = 0
- **Agresivity of 1**: a ∨ 1 = 1
- **Idempotency**: a ∧ a = a, a ∨ a = a
- **Absorption of Negation**: a ∨ (¬a ∧ b) = a ∨ b, a ∧ (¬a ∨ b) = a ∧ b
- **Double Negation**: ¬¬a = a
- **Complementarity of 0 and 1**: ¬0 = 1, ¬1 = 0
- **De Morgan Law**: ¬(a ∧ b) = ¬a ∨ ¬b, ¬(a ∨ b) = ¬a ∧ ¬b
## Example of Bool Algebra
- **Trivial Algebra**:
	- **0 = 1** (they contain only one element)
	- all operation have the same outcome
- **Algebraic Statements**:
	- **0 is false**, **1 is truth**
	- **∧ is conjunction**, **∨ is disjunction**, **¬ is negation**
- **Set Algebra**:
	- **0 is empty set** (∅), **1 is an universum** (U)
	- **∧ is intersection**, **∨ is union**, **¬ is complementary**
- **Electric Circuit Algebra**:
	- **0 is low** (log. 0), **1 is high** (log. 1)
	- **∧ is AND**, **∨ is OR**, **¬ is NOT**
## Functions
There are **2^2^2 functions** (16) that can be realized over Bool's algebra. So of these are mapped onto numbers, but they can be also described as with their corresponding symbols in this diagram:
![[Logic_Gates_Diagram]]
### NOT
Negation or Complement

| X   | O   |
| --- | --- |
| 0   | 1   |
| 1   | 0   |
### Repeater
Repeats the input and realizes **identity**. Can be used as buffer.

| X   | O   |
| --- | --- |
| 0   | 0   |
| 1   | 1   |

### OR
Disjunction or Union

| X   | Y   | O   |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 1   |
| 1   | 0   | 1   |
| 1   | 1   | 1   |
### AND
Conjunction or Intersection

| X   | Y   | O   |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 0   |
| 1   | 0   | 0   |
| 1   | 1   | 1   |
### NOR
Negated Disjunction or **Pierce's Function**

| X   | Y   | O   |
| --- | --- | --- |
| 0   | 0   | 1   |
| 0   | 1   | 0   |
| 1   | 0   | 0   |
| 1   | 1   | 0   |
### XOR
Negated Equivalence or **Exclusion Disjunction**

| X   | Y   | O   |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 1   |
| 1   | 0   | 1   |
| 1   | 1   | 0   |
### NAND
Negated Conjunction or **Sheffer's Function**

| X   | Y   | O   |
| --- | --- | --- |
| 0   | 0   | 1   |
| 0   | 1   | 0   |
| 1   | 0   | 0   |
| 1   | 1   | 0   |
### XNOR
Negated Exclusion Disjunction or **Equivalence**

| X   | Y   | O   |
| --- | --- | --- |
| 0   | 0   | 1   |
| 0   | 1   | 0   |
| 1   | 0   | 0   |
| 1   | 1   | 1   |
## Sheffer's Function
Using the Sheffer's function is possible to create all other possible function of the Bool's algebra, such as:
- **¬x** = **¬(x ∧ x)**
- **x ∧ y** = **¬(¬(x ∧ y))** = **¬( ¬(x ∧ y) ∧ ¬(x ∧ y) )**
- **x ∨ y** = **¬(¬x ∧ ¬y)** = **¬( ¬(x ∧ x) ∧ ¬(y ∧ y) )**
- **x → y** = **¬x ∨ y** = **¬(x ∧ ¬y)** = **¬(x ∧ ¬(y ∧ y))**
## Pierce's Function
Using the Pierce's function is possible to create all other possible function of the Bool's algebra, such as:
- **¬x** = **¬(x ∨ x)**
- **x ∧ y** = **¬(¬x ∨ ¬y)** = **¬( ¬(x ∨ x) ∨ ¬(y ∨ y) )**
- **x ∨ y** = **¬(¬(x ∧ y))** = **¬( ¬(x ∧ y) ∨ ¬(x ∧ y) )**
- **x → y** = **¬x ∨ y** = **¬(x ∨ x) ∨ y** = **¬(¬(¬(x ∨ x) ∨ y)) ∨ ¬(¬(x ∨ x) ∨ y)))**

![[Venn Diagrams]]