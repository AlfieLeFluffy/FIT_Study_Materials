Special formats that allow representation of real number to some degree of precision.
## Fixed Decimal Point
For representation of of positive real numbers. There is a fixed about of bit for representing the whole and the decimal parts of the number. Today it is not commonly used. 
	For example 5 bit for whole and 3 bit for decimal can be 00101001 = 5.125
## Floating Point - IEEE754
Most commonly used format for decimal numbers today. It consists of three components:
- **Sign bit** (S) - [[MSB]] with 1 for negative and 0 for positive
- **Mantise** (M) - is represented in [[Whole Number Representation#Direct (přímý) code|Direct Code]] and contains an **implicit 1 at the beginning**
- **Exponent** (E) - is represented in [[Whole Number Representation#Additive (přímý s posunutou nulou) code|Additive Code]] which allows to represent positive and negative exponent
- Base (B) - is implicitly 2
**IEEE754** defines the storing of floating point numbers as a sequence starting with sign bit, then exponent and then mantise. There are two versions defined both differing in precision and range.
### Versions
#### Single Precision
Uses 32 bits to represent a number with 8 bits for the exponent which is moved by -127 (half the range) and 23 bits to represent the mantise. [[MSB]] is the sign bit. It is precise for 7 decadic numbers and has a range of 〈-2<sup>127</sup>, 2<sup>127</sup>).
#### Double Precision
Uses 64 bits to represent a number with 11 bits for the for the exponent that is moved by -1023 (half the range) and 52 bits for the mantise. [[MSB]] is the sign bit. It is precise for 16 decadic numbers and has a range of 〈-2<sup>1023</sup>, 2<sup>1023</sup>).
### Explicit One
In the mantise it is not required to explicitly write the first 1 of the number as it will be there either way. So a to store a number 1.011 -> 011 it would skip the first 1. 
## View Error (Chyba Zobrazení)
As decimal numbers in the [[Binary System]] are represented with a sum of fractions it is not entirely possible to represent all decadic numbers on a finite amount of bits. For example the number 0.1 cannot be fully represented which is a common issue in financial software, which require higher precision and usually use different ways to represent numbers in different codes. For this they can use for example [[Binary Coded Decimal Code (BCD)]].