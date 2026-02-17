---
tags:
  - TIN
aliases:
  - context-free pimping lemma
---
### Context-Free Pumping Theorem
If $L$ is a context-free language, then there exists constant $k>0$ such that if $z\in L$ and $|z|\geq k$, then $z$ can be written in form of:
$$z = uvwxy, uv\not= \epsilon,|vwx|\leq k$$
and for every $i\geq 0$ it applies that $uv^iwx^iy \in L$.
An equivalent formulation of the Pumping lemmat is:
$$L\in \mathcal{L}_{2}\implies \exists k>0:$$
$$ \forall z \in \Sigma^*:  z\in L\wedge|y|\geq \implies$$
$$(\exists uvwxy\in \Sigma^*:z=uvwxy\wedge vx\not= \epsilon \wedge|vwx|\leq k\wedge \forall i\geq_{0}:uv^iwx^iy\in L)$$
#### Proof
If $L=L(G)$ and $G$ is [[Context-Free Grammar]] in the [[Context-Free Grammar#Chomsky's Normal Form|Chomsky's Normal Form]], then:
1. First proof of the implication $A\implies^+w$ for some $A\in N$, $w\in \Sigma^*$, then $|w|\leq 2^{m-2}$, where $m$ is the number of vertexes of the longest path in the derivation tree. This implication is true, because $|w|$ is equal to the number of direct leaf predecessors of the specific derivation tree, that is at max equal to number of leaves of the full binary tree, because all branches contain $m-1$ vertexes, which is exactly $2^{m-2}$.
2. We can set $k=2^{|N|}>0$ and we are considering any brach $z$ such that $|z|\geq k$. If we set $m$ as the number of vertexes of the longest path in the corresponding derivation tree then $2^{|N|} \leq 2^{m-2}$ and such path then contains at least $|N|+2$ vertexes ($|N|+2\leq m$). From these $|N|+2$ vertexes is one terminal symbol and at least two are set by the same non-terminal symbol $A$. String $v,x$ cannot be empty, otherwise the applied rule would have a form of $A\to BC$. Now lets expect the derivation of $z$ of form $S\implies^*uAy\implies^+uvAxy\implies^+uvwxy=z$. This also means that in the grammar G there can also be made the derivation $S\implies^*uAy\implies^+uvAxy\implies^+uvvAxxy\implies^+uv^2wx^2y$, because $A\implies^+w$ is a provable statement. 