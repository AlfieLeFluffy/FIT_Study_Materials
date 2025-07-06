Representation of whole number with a sign (+ or -) always half's the absolute numbers range as one bit is required to represent the sign, but adds the option for negative numbers, which means that the overall range remains intact, just is shifted half down.
## Versions
The representation of the sign can be done in several ways some of which are:
### Direct (přímý) code
The first bit of the number is reserved for the sign (sign bit). This can be either 0 for positive numbers or 1 for negative numbers. A problem with this code is that there exist two zeros (+0, -0). This code is for example used in [[Decimal Number Representation#Floating Point - IEEE754|IEEE754]] to represent the exponent (10000001 = -1). Code also complicates addition and subtractions.
### Additive (přímý s posunutou nulou) code
The number is usually in some way in offset. This means that for example the number -127 can be 00000000, so 01111111 is 0 and 11111111 is 128. The con of this approach is that due to the difference between + and - numbers means that multiplication is difficult and requires subtractions of set constants. Addition and subtraction work without an issue.
### Inverse (jedničkový doplňkový) code
Negative values are represented by negating all bits and keeping the [[MSB]] as a sign bit, either 0 for positive values or 1 for negative. For example 0101 = 5 and 1010 = -5. Code complicates addition and subtraction as it is deferent from normal numbers and has the double zero issue.
### Two's complement (dvojkový doplňkový) code
Positive number is represented as normal and negative number is represented by negating the bits of a positive number and adding 1. This is the most used format as it has only one zero. Addition and subtraction can be realized the same ways non signed number and for multiplication the only things necessary is to replicate the [[MSB]] to double the range.