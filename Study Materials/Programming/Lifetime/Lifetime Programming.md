---
tags:
  - FLP
aliases:
  - lifetime programming
sources:
  - "[[FLP_03_Rust.pdf]]"
---
Lifetime programming is a combination of the classical [[Imperative Programming]] and [[Functional Programming]], borrowing from both worlds things that insure the data validation/safety of functional and the freedom/simplicity of imperative.
These languages usually have a rather strong compilators that check lifetimes of data/data structures ahead of compiling and warn ahead regarding issues such as incompatible data types, freeing of data structures ahead of their use, etc.
An example of such language is [[Rust]].
## Characteristics
Some of the common characteristics of these languages (based on [[Rust]] implementation) are:
### Ownership
Ownership is explained within [[Rust#Ownership| Rust Ownership]].
### Lifetime
A generic concept that is ensuring that references are valid as long as we need them to be instead of ensuring that a type has the behavior we want. More about lifetime implementation can be found in [[Rust#Lifetime|Rust Lifetime]].