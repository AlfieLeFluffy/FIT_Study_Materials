Each **regular grammar describes a** [[Regular Language]]. It is an ordered quartet **(T, N, P, S)**, where:
- **T** is a final set of terminal symbols.
- **N** is a final set of non-terminal symbols.
- **P** is a final set of rules in the form of **X -> wY**, **X -> w**, **S -> ε** 
- **S** is a start symbol.
There exists **right** (X -> wY) and **left** (X -> Yw) regular grammars, that are equivalent, but they cannot exist combined.
	Example can be: **G = ( {a, b}, {A, B, C}, P , A)** where **P = {A -> ε | aB, B -> bC, C -> a}**