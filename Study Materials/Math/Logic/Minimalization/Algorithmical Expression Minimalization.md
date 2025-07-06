Algorithmical logic expression minimalization uses predefined algorithms to minimalize logic expressions. These methods are easier for both humans and computers to implement, especially with complex expressions.
## Quine McCluskey
This algorithm using a tabular method, which is useful for functions that require multiple variables (4+). Can be done both for disjunctive and conjunctive final expressions, but the one describe bellow is for disjunctive.
## Steps
1. Write out and order entries that result in log.1 into groups by the amount of log. 1s in their variables.
2. Eliminate variables that are different only in place from neighbouring groups. Instead of this variable write a dash (-). If the term has not neighbours and no variable can be eliminated then its the shorten term.
3. If a variable was eliminated from a term then return to step one with such terms.
4. To find the minimal result (expression) for given function use a table of implicants.
	1. Write down the shortened terms into the table (all variables that are not a dash with zeros negated)
	2. Select columns where there is only one option.
	3. Add those terms together for the final expression.