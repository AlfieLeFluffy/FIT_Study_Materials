Gray code uses sequential binary numbers in such a way that there is only one changed bit between each increment. This reduces operations necessary to increment or decrement the counter to only once change.
To convert a binary representation of a number into Gray Code the following algorithm can be used: 
- The Most Important Bit (MSB) stays the same.
- For every bit you calculate: **g<sub>i</sub> = b<sub>i+1</sub> xor b<sub>i</sub>**
For example, the conversion of binary number 1110 to Gray code it would end up as 1001.