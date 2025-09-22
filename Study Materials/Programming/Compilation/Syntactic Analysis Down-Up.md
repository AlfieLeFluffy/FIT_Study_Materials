---
tags:
  - IFJ
---
Syntactic analysis from down-up uses right parsing, meaning it uses reverse order of rules, that are used in the rightmost derivation for the input [[String|string]]. We can divide these analyser into **precedence syntactic analysers**, which are weaker but easier to implement, and **LR syntactic analysers**, which are more robust but also more complex to implement.
## Implementation of Down-Up Analysis
### Precedence Syntactic Analyser
There must **not exist** any rules with the **same right side of rules** and the grammar must **not contain any ε rules**.
For this type of analysis we use a **precedence table**, which is set by **asociativity** and **precedence operators**. This is most commonly used for syntactic analysis of logic and mathematic expressions.