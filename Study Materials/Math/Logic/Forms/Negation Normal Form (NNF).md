The formula is in Negation Normal Form when it applies that the forms has:
1. Contains only logical symbols (conjunctions): **0, 1, ¬, ∧, ∨**
2. **Negation ¬** is only **in front of variables**.
### Steps
To turn a normal formula into NNF we can use these steps:
1. We turn **biconditionals** into **implications** through:
	`x ↔ y -> (x → y) ∧ (y → x)`
2. We reduce **implications** through:
	`(x → y) ->  ¬x ∨ y`
3. We use **De Morgan's Law** to get right of implications in front of parentheses:
	`¬(a ∧ b) = ¬a ∨ ¬b`
	`¬(a ∨ b) = ¬a ∧ ¬b`
4. We eliminate **double negation**.