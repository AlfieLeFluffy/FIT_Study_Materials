---
tags:
  - TIN
aliases:
  - Turing machine coding
  - TM coding
sources:
  - "[[TIN_04_Turing_Machine.pdf]]"
---
A [[Turing Machine|Turing machine]] can be encoded into a string that is understandable and can be simulated on a [[Universal Turing Machine|universal Turing Machine]]. This coding must include:
- **States** including $q_{0},q_{f}$
	- States can be ordered into a sequence $q_{0},q_{f},q_{1},q_{2},\dots$, where each state then can be encoded as $0^i$ with $i$ being their position in the sequence.
- **Symbols** of both $\Sigma$ and $\Gamma$
	- Symbols are encoded in a similar fashion to states, but with a different start $\Delta,L,R,a_{i}\dots$.
- Transitional **function** $\sigma$
	- Transitions $\sigma(p,x)=(q,y)$ are represented by a four-tuple $(p,x,q,y)$, each element is divided by a dividing symbol (usually $1$) into $p \ 1 \ x \ 1 \ q \ 1 \ y$ and then each part is separately encoded into their respective state or symbol codes.
The entire [[Turing Machine|Turing machine]] is then encoded as a sequence of transitions between states divided by a dividing symbol, which is usually a $1$.