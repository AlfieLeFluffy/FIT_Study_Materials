---
tags:
  - MUL
aliases:
  - AE
  - arithmetic encoding
sources:
  - "[[MUL_02_Compression_Techniques.pdf]]"
---
Arithmetic encoding uses a thinning interval to encode data.
### Example
Best way to understand this concept is an example such as:
- There are 3 encoded symbols: A, B, C
- The ration of them appearing is: 4-2-2
- We can convert this into intervals as:
	- A: 0-50%
	- B: 50-75%
	- C: 75-100%
- We take the encoding interval 0-1
- The encoded text is: AABAC
- The first character is A and so we take the interval 0-50% from the encoding interval, which is 0-0.5, which is our new encoding interval.
- The second character is again A and we take the 0-50% interval and we get 0-0.25.
- In order to get 0-0.25 the only path was that the first two characters were A.
- Now we take the third character B, which is 50-75% and we get 0.125-0.375. To this interval we can once again only get by encoding the characters AAB in that sequence and no other.
- In this manner we continue until we encode the entire thing.
## Characteristics
This algorithm:
- Is rather robust
- Quick
- High compression
## Implementation
In implementation the intervals are not floating point calculations as they would suffer from performance and eventual loss in accuracy, which would lead to errors. In implementations these calculations are usually done over large integer values.