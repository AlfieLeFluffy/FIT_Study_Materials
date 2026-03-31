---
tags:
  - IPT
  - MSP
aliases:
  - basic probability
  - Probability
  - probability
---
## Definitions
Some basic definition regarding probability are:
### Probability Space
**Ω** is the set of all possible values that a **random value X** can become and is also called the **probability space**. A probability space for sequential coin tosses looks like **Ω = {(heads, heads), (heads, tails), (tails, heads), (tails, tails)}**.
### Random Phenomenon
Is any subset of the **probability space Ω**:
- Phenomenon is impossible is the set is empty. In the given conditions there is not state in which the phenomenon becomes true.
- Phenomenon is certain if the subset is equal to the probability space.
#### Intersection of Phenomenon
An intersection of phenomenon **A** and **B** is a phenomenon that will occur once both phenomenon **A** and **B** happen simultaneously. We can note it as **A ∩ B** and if **A ∩ B = ∅** then we say these phenomenon's are **disjunctive**.
#### Unification of Phenomenon
An unification of phenomenon **A** and **B** is a phenomenon that will occur once at least one phenomenon **A** and **B** happens. We can note it as **A ∪ B**.
#### Opposite Phenomenon
Is the complementary phenomenon to a phenomenon **A** and happens when phenomenon **A** does not happen. We note is as **A’** and it applies that **A’ = Ω \ A**.
### Full Phenomenon System
Phenomenon's **A1, B1, ...**  create a full phenomenon system if **A1 ∪ A2 ∪ ··· = Ω**. Additionally it applies that if **Ai ∩ Aj = ∅, ∀i != j** then we say it is a **full system of disjunctive phenomenon's**.
### Axiomatic Definition of Probability
If **(Ω, A)** is a phenomenon array and P is set function defined on **A** with properties:
- **P(Ω) = 1**
- **P(a) >= 0 ∀a ∈ A**
- If **Ak ∈ A, k = 1, 2, ...** are disjunctive phenomenons.
Then we can say that:
$$
P( unification \ of \ A) = \sum_{i=1}^{\infty} P(A_{i})
$$
Function P is the **probability function** and the triple **(Ω, A, P)** is the **probability space**.
### Classical Definition of Probability
Classical probability is defined as the **division** (ratio) of **amount of all favourable phenomenons** against **amount of all possible phenomenons**.
$$
P(A) = \frac{|A|}{|\omega|}
$$
Where:
- **|A|** is the number of elements of a set of favourable phenomenons.
- **|Ω|** is the number of elements of a set of all possible phenomenons, probability space.
### Probability Properties
If **(Ω, A, P)** is the **probability space** then for **P** the properties are:
- **P(∅) = 0**
- **a, b ∈ A, a ∩ b = ∅** ⇒ **P(a ∪ b) = P(a) + P(b)**
- **a, b ∈ A** ⇒ **P(a ∪ b) = P(a) + P(b) - P(a ∩ b)**
- **a, b ∈ A, a ⊂ b** ⇒ **P(b - a) = P(b) - P(a)**
- **a, b ∈ A, a ⊂ b** ⇒ **P(a) <= P(b)**
- **a ∈ A** ⇒ **0<= P(a) <= 1**
- **a ∈ A** ⇒ **P(a') = 1 - P(a)**
- **a1, a2, ... ∈ A** ⇒ **P(∪ ai) <= ∑ ai**
### Conditional Probability
A probability of some experiment is dependent on the another probability. If **(Ω, A, P)** is the **probability space** and **b ∈ A, P(b) > 0** then:
$$
P(a|b) = \frac{P(a \ ∩ \ b)}{P(b)}
$$
We can say that this is a **conditional probability** of phenomenon **a** under the condition that phenomenon **b** happened.
#### Bayes' Formula
If we have phenomenons **a** and **b** and **P(b) != 0** then it applies that:
$$
P(a|b) = \frac{P(b|a)P(a)}{P(b)}
$$
### Addition of Probability
If phenomenons are independent of each other their intersections are going to be **zero**.
$$
P(A ∪ B ∪ C) = P(A) + P(B) + P(C) - P(A∩B) - P(B∩C) - P(A∩C) + P- P(A∩B∩C)
$$