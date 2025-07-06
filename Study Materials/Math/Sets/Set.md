A set is mathematical structure of **unique** (un-repeated) objects that take as a whole. A set is clearly determined by its elements and their order does not influence that. Sets can also be **empty**, **infinite** or **finite**.
## Element Amount
As said before sets can be either:
- **Infinite** sets have an uncountable amount of elements such as a **real number**.
- **Finite** sets have a countable amount of elements that end. They are **distinct** ([[View|Bijective View]]) with some subset of **natural** numbers.
## Notation
We commonly signify sets with upper-case letters and their elements with lower-case letter such as **A = {a, b, c}**. If an element of a set we signify that by ∈ such as **a ∈ A**. If an element is not part of the set we signify it the same way but we cross over the symbol with a line.
There are several ways to note down a set such as:
- **By Listing out Elements**: A = {42, a, 10}
- **By a Predicate**: B = {2<sup>n</sup> | n ∈ N}
- **By an Interval**: C = <0, 1> or C = (0, 1) where <> means the end element is included and () is excluded.
- **Known Sets**: N natural, Z integer, Q rational, R real, C complex, ∅ empty
### Potential Set
Potential set of set **X** is **P(X)** and contains all possible subsets of the set **X**. If a set **X** is finite and its monumentality is **|X| = n** then the potential set will contain **2<sup>n</sup>** elements.
```
A = {1, 2, 3}
P(A) = {∅, {1}, {2}, {3}, {1, 2}, {1, 3}, {2, 3}, {1, 2, 3}}
```
### Empty Set
An empty set **∅** is a set that does not contain any elements.
### Subset
A subset is a set that contains only elements that can be found in another set. If a set **A** contains only elements that can be found in set **B** such as **A = {1, 2}** and **B = {1, 2, 3, 4}**, then we can say that A is a subset of B, which is noted as **A ⊂ B**. If the subset can be the same as the set we notate this same as greater/lesser or equal to **⊆**.
### Closeness of Operations
Set **M ⊂ A** is closed against algebraic operations if operations return a value of the set **M**. This means that operations over the set will only return values that are also part of the set.
### Decomposition
Decomposition of sets is created when a system of sets (a set of sets) where unification would return the original set. This means that **intersection** of these sets is an empty set.
## Set Operations
We can use several operation with sets such as:
- **Intersection ∩** finds all elements of two sets that these sets share.
- **Unification ∪** combines all elements of two sets (gets rid of duplication).
- **Difference /** finds all elements that are in one subset, but are not in the other: `A = {1, 2, 3}, B = {2, 3, 4,}, A / B = {4}`
- **Symmetrical Diference** finds all elements two sets do not share: `A = {1, 2, 3}, B = {2, 3, 4,}, A ∆  B = {1, 4}`
- **Complement** finds all missing elements of a subset that are present in a set. `A = {1, 2, 3}, B = {2}, B^c = {1, 3}`
### Operation Properties
- **Commutativity** in binary operations is the ability to change the order of operands without influencing the outcome (this does on apply for Difference) `A ∪ B = B ∪ A`.
- **Association** in binary operations means the is does not matter in which order of the same type are carried out without influencing the outcome `(A ∪ B) ∪ C = A ∪ (B ∪ C)`.
- **Distribution** in binary operations means that one operation can be distributed through another operation `A ∩ (B ∪ C) = (A ∩ B) ∪ (A ∩ C)`.