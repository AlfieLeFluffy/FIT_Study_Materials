Regular expression is an expression in which operators **.**, **+** and **\***, that signify **concatenates**, **unification** and **iteration**. Regular expressions describe a [[Regular Language|regular languages]]. If there is an alphabet **Σ** then a regular expression over this alphabet and its languages, that it signifies, is defined as:
- **∅** is a regular expression
- **ε** is a regular expression of language **{ ε }**
- **a, a ∈ Σ** is a regular expression of language **{ a }**
- If **r** and **s** are regular expressions that signify languages **Lr** and **Ls** then:
	- **(r.s)** is a regular expression signifying **L = LrLs**
	- **(r + s)** is a regular expression signifying **L = Lr ∪ Ls**
	- **(r\*)** is a regular expression signifying **L = Lr\***
	The parenthesis can be eliminated by priority such as **\* > . > +**.