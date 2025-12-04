---
tags:
  - IFJ
  - TIN
aliases:
  - ESA
---
This is [[Stack Automata]] that **can read the entire string stored on the stack**. This means that rules can include multiple symbols from the stack on their left side. Stack automata and expanded stack automata are equivalent. A transitional function for ESA can be defined as:
$$\sigma: Q \times(\Sigma\cup \{ \epsilon \}\times \Gamma^*\to 2^{Q\times \Gamma^*})$$