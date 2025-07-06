Convertors allow communication with an analog world. This means that analog values can be converted (parsed) into binary (digital) values and back. This can for example be used in to convert a analogue value out of a temperature sensor into digital values that can be converted into temperature.
## Types
There are two types of convertors:
### AD Convertor (Analog-To-Digital)
Converts analogue values into digital ones. The measured value that the convertor returns are in between **0 - 2<sup>N-1</sup>** and must be converted into the equivalent voltage. There exists multiple types of AD convertors but some are:
#### Flash ADC (Direct-Conversion ADC)
Consists of only a [[Combination Circuit]] that converts given values in parallel and with a constant speed. N sized convertor is created with 2<sup>N-1</sup> comparators that are connected to a voltage ladder and a reference voltage. The outputs of these comparators are connected to a priority coder.
This approach has its benefits such as speed, but is more expensive and rigid in its design.
#### Approximation ADC
This type of ADC is done through a [[Sequence Logic Circuit]], where the input must be sampled. It works based on halfling of a interval. It starts with a reference voltage value, that is converted into analog value, compared with the input and then depending on if the result is higher or lower it add or subtracts half of the current value tested for.
### DA Convertor (Digital-To-Analog)
Converts digital values into analog ones, most commonly done through a R-2R resistance ladder. 