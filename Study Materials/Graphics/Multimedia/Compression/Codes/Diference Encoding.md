---
tags:
  - MUL
aliases:
  - DE
  - diference encoding
sources:
  - "[[MUL_02_Compression_Techniques.pdf]]"
---
An encoding type that instead of encoding the symbols directly, encodes their differences.
## Characteristics
Basic DE characteristic are:
- Relative encoding, delta encoding
- This encoding type is usually used as a part of more complex methods.
- Substitution of input values for their differences with their predecessors.
- Easy prediction method and can also be used to encode prediction error.
- An example can be: `17 16 18 32` -> `-1 +2 +14`