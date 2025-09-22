---
aliases:
  - numeric system
  - number system
---
Number systems are a way of representing numbers. We divide these system into two categories depending on how we interpret the symbols in the number system:
- **Non-positional**
- **Positional**
## Non-positional Number Systems
Non-positional systems are systems in which the position of the symbols representing the number are not dependent on their position within the number [[String|string]]. An example of such system is [[Roman Number System]].
## Positional Number Systems
Positional systems are system in which the position of the symbols in representing the number are dependent on their position within the number [[String|string]]. These system are most common nowadays. All positional system **require a symbol for zero**. These system also support fractional (decimal) numbers, which are usually separated by some special character like a dot. Examples of such system are [[Decadic Number System]], [[Binary Number System]], etc.
### Base (Radix)
A number defining the maximum amount o numeric symbols that are available in a system. These are for example $r=10$ for [[Decadic Number System|Decadic System]] and $r=2$ for [[Binary Number System|Binary System]].
### Conversion between Positional Systems
Commonly a way to convert from one positional system to another the [[Decadic Number System|decadic system]] is used as a middle-man system to simplify the translation. Another common way to convert in positional systems is through a common exponential base.
#### Substitution
Substitution can be used for any positional system and it is the most intuitive and easiest to use for the [[Decadic Number System|decadic system]]. The system converts a number within another system into a polynomial equation where the numeric number is multiplied by the radix to the power of the places within the number.
For example the number 1010 in binary can be converted into:
$$1*2^3+0*2^2+1*2^1+0*2^0 = 8 + 2 = 10$$
#### Division by Base
This conversion is best used in whole numbers. It works by dividing the converted number by the other systems radix, until the calculations hit 0, and noting down the remnants after each calculation, which then if put into reverse sequential order form the target number in the target system.
For example the number 10 in decadic cen be converted into binary as:
$$10 / 2 = 5 \ \text{rest 0}$$
$$5 / 2 = 2 \ \text{rest 1}$$
$$2 / 2 = 1 \ \text{rest 0}$$
$$1 / 2 = 0 \ \text{rest 1; MSB}$$
Which if pust into the reverse sequential order gives us 1010 in binary.
#### Subtraction by Base
This conversion is useful for conversion of fractional numbers. It works by subtracting the fractional number (number must be less then 1 so numbers bigger then 1 are divided and converted separately) by the target system radix to the power of the target fractional position (^-1, ^-2, ^-3). Every time the subtraction result is equal or greater to 1 then we note it down, remove it from the number and continue multiplying until we hit 0 or we find our desired precision. The noted number are then sequentially put together and result in the target number in the target system.
For example the number 0.625 can be converted into binary as:
$$0.625 - 2^{-1} = 1.125 \ ; \ 0.125 \ \text{res 1}$$
$$0.125 - 2^{-2} = 0.125 \ ; \ 0.125 \ \text{res 0}$$
$$0.125 - 2^{-3} = 1 \ ; \ 0 \ \text{res 1}$$
So the result will be 0.101 in binary.
#### Conversion through Common Base
These conversion are most common between systems that use a common base such as 2 with [[Binary Number System]], [[Octadecimal Number System]], [[Hexadecimal Number System]].
The conversion is done through the base numeric system so hexadecimal to octadecimal is done through binary for simplicity. This is done by grouping together several numeric positions of the base system together as one position within the original or target system.
An example of this could be conversion of 10101 in binary into octadecimal:
$$10101_{2} \to (010|101)_{2} \to (2|5)_{8} \to 25_{8}$$
When done in reverse the step are similar only in reverse, for example 163 in binary into binary:
$$163_{8} \to (1|6|3)_{8} \to (001|110|011)_{2} \to 1110011_{2}$$
This can also be done for hexadecimal as well:
$$1101001_{2} \to (0110|1001)_{2} \to (6|9)_{16} \to 69_{16}$$
$$1B5_{16} \to (1|B|5)_{16} \to (0001|1010|0101)_{2} \to 110100101_{2}$$
