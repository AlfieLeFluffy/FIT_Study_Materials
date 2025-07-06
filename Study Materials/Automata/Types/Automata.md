Automata (konečný automat KA) is an ordered sextuplet **M = (S, Σ, Λ, T, G, s<sub>0</sub>)**, where each element represents:
- **S** is a finite non-empty set of states (internal alfabet)
- **Σ** is a finite input [[Alphabet]]
- **Λ** is a finite output [[Alphabet]]
- **T** is a state change function (T: S * Σ -> S, which means that for a state there can be a input character in the input alfabet that changes the state to another or the same state)
- **G** is the output (final state) function (G: S * Σ -> Λ for Mealy SM and G: S -> Λ  for Moor's SM)
- **s<sub>0</sub>** is the starting state and s<sub>0</sub> ∈ S (is part of the internal alfabet)

## Electronic Elements
There are there many components a state machine must have:
- **Next-state logic** (transition function) is combinatory logic circuit responsible for changing the current state to a new state based on the current memory (state) and the input.
- **Memory** keeps the current state and is usually made by a [[Register]].
- **Output** depends on the type of SM and can be either Mealy, Moor, or combined.
## Types
### Mealy's Automata
The output is a function of both the current state and the input: **Y = f(X, Z)**.
	In practice this means that each edge (changes of state) is denoted not only by input, but also the value that should be outputted. Example could be if we have states A and B and there is a state change function A * 1 -> B and an output function A * 1 -> 0. So the edge is denoted as 1/0 (input/ouput).
![[Mealy_Automata]]
### Moore's Automata
Out of the state machine is only dependent only on the current state of the SM: **Y = f(Z)**.
	Example could be if we have states A and B and there is a state change function A * 1 -> B and an output function A -> 0. So the edge is denoted as 1 (input) and the output is denoted on the state node by 0.
![[Moors_Automata]]

### Combination Automata
Combines both a Moor's and Mealy's Automata into one.