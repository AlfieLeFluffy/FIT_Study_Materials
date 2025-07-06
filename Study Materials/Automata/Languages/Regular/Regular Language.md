A Regular [[Language]] is the simplest Formal Language in the frame of [[Chomsky Hierarchy]]. Over the alphabet **Σ** we can define them as:
- Empty language **Ø** is regular.
- For each **a, a ∈ Σ**, language **{ a }** is regular.
- If languages **A** and **B** are regular then their **unification**, **concatenate** and **iteration** are also regular.
- No **other languages are regular**.
Another ways of proving a language is regular are:
- There exists a [[Finite Automata]] (deterministic or otherwise) that accepts all words of this language.
- Exists a [[Regular Expressions]] that this language generates.
- Exists a [[Regular Grammar]] that this language generates.
To check if a language **is NOT** a regular language we can use a [[Pumping Lemma]] method.