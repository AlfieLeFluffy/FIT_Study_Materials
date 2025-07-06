A structural notation for describing and generating [[Context-Free Language]]. This grammar is used for describing and analysing programming languages (compiler's parser) and sets of string related to this. It is an ordered quartet **G = (T, N, P, S)**, where:
- **T** is a final set of **terminal** symbols.
- **N** is a final set of **non-terminal** symbols where **N ∩ T = ∅**.
- **P** is a final **set of rules** in the form of **A -> x** where **A ∈ N**, **x ∈ (N ∪ T)\***.
- **S ∈ N** is a start symbol.
	- An example could be **G = ({S}, {a, b}, P, S)**, where **P = {S -> ε, S -> aSb}**.
	- Which can generate the language **L(G) = {(a<sup>n</sup>b<sup>n</sup>: n > 0)}**.
The princip is that the grammar can use rules on non-terminal symbols to generate the language. If **uAv -> uxv** in **G** then we can say that **G** makes a derivation step from **uAv** to **uvx**.
### Derivation Direction
Either of these directions can generate the same outcome, just in a different order.
- **Most-Left Derivation** uses the most left non-terminal to derivate.
- **Most-Right Derivation** uses the most right non-terminal to derivate.
