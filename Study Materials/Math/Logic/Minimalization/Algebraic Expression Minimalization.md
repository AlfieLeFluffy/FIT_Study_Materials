Algebraic logic expression minimalization uses (applies) axioms of [[Bool's Algebra]]. This is a more demanding process especially for complex expressions.

## Bool's Algebra
![[Bool's Algebra#Axioms]]
## Theorems
These theorems are derived from [[Bool's Algebra]] axioms and define some useful properties that can be used while minimizing a logic expression. They are:
- **Uniqueness** of 0 and 1
- **Idempotence**: `a + a = a, a * a = a`
- **Agresivity** 1 and 0: `a + 1 = 1, a * 0 = 0`
- **Absorption**: `a + a * b = a, a * (a + b) = a`
- **De Morgan's Law**: `(a + b)' = a' * b', (a * b)' = a' + b'`
- **Association**: `(a + b) + c = a + (b + c), (a * b) * c = a * (b * c)`
- **Double Negation**: `a'' = a`
- **Absorption of Negation**: `a + a' * b = a + b, a * (a' + b) = a * b`
## Forms
The final products of these minimalization operations can take many forms, but there are two important ones:
![[Sum of Products (DNF)]]

![[Product of Sums (CNF)]]

Minimal version of both forms (MNDF, MNKF) are those that from which no term can be eliminated.

