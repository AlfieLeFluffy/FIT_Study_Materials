---
tags:
  - MUL
aliases:
  - RLE
  - run-length encoding
sources:
  - "[[MUL_02_Compression_Techniques.pdf]]"
---
Encodes sequences (series) of same symbols with many modifications. 
## Characteristics
Basic characteristics of RLE are:
- This encoding type is usually used as a part of more complex methods.
- The code keeps information about the encoded symbol and the amount of repetitions.
- The symbols forming the sequence can be variable in size from one character to entire strings.
- It is used in formats such as BMP, PCX, TIFF, TGA, JPEG, bzip2, etc.
- An example of this format can be: `AAAABCD` -> `4xABCD`
