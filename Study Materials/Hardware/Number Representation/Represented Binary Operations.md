These operations use either [[Whole Number Representation]] or [[Decimal Number Representation]].
## Addition
### Whole Numbers
Addition of whole numbers is done the same way as is done in the [[Decadic System]], but it is possible the number overflows.
### Floating Point
Floating point addition is not associative as a result of rounding error. In IEEE754 the numbers first need to be put to the same exponent. The number with the lower exponent is always transformed to the higher exponent.
## Subtraction
### Whole Numbers
In the processor this is realized by negating one of the [[Operand]]s and settings C<sub>0</sub> to one, practically converting the number into [[Whole Number Representation#Two's complement (dvojkový doplňkový) code|Two's Complement]]. This is also more natural for humans to calculate.
### Floating Point
Floating point addition is not associative as a result of rounding error. In IEEE754 the numbers first need to be put to the same exponent. The number with the lower exponent is always transformed to the higher exponent.
## Multiplication
### Whole Numbers
In whole numbers the multiplication can result in the number doubling in size, which requires. When multiplying numbers in [[Whole Number Representation#Two's complement (dvojkový doplňkový) code|Two's Complement]] it is necessary to expand the numbers with their [[MSB]]. It is also preferable to multiply numbers in [[Whole Number Representation#Two's complement (dvojkový doplňkový) code|Two's Complement]] for signed numbers.
### Floating Point
For floating point the numbers is the result of several steps:
- Sign bit is the result of a XOR operation with the sign bits.
- Exponent is the result of addition between exponents.
- Mantise is the result of whole number multiplication that are expanded with the implicit 1.
## Division
### Whole Numbers
In a computer a whole number division is a complex operations that is done through several methods. Signed division can be done with absolute values and then the sign can be added at the end.
