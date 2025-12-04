---
tags:
  - TIN
  - to_be_finished
aliases:
  - M-N Theorem
  - M-N
---
Myhill-Neroda theorem is a rule about [[Regular Language|regular languages]] and [[Finite Automata|finite automata]].
## Definition
If **L** is a [[Formal Language|language]] over [[Alphabet|alphabet]] **Σ**, then the following expressions are equivalent:
1. **L** is a language accepted by a [[Finite Automata|deterministic finite automata]].
2. **L** is union of some classes of decomposition determined by right (true) congruence of **Σ\*** with a finite index (number of classes).
3. Relation **∼<sub>L</sub>** has a finite index (number of classes).
### Right Congruence
If **Σ** is an [[Alphabet|alphabet]] and **∼** is equivalence over **Σ\***. Equivalence ∼ is right (true) congruence if for each word $u,v,w \in \Sigma^*$ applies:
$$u∼v \implies uw∼vw$$
### Prefix Equivalence
If **L** is any [[Formal Language|language]] over [[Alphabet|alphabet]] **Σ**; over [[set]] **Σ\*** we define relation **∼** called *prefix equivalence* for **L** such that:
$$u∼_{L}v \implies \forall w \in \Sigma^*: uw \in L \implies vw \in L$$