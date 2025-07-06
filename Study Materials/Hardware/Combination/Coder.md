Coder transforms (encodes) information from **N** inputs to **K** outputs based upon a combination table. It is complimentary circuit for the [[Decoder]]. 
Generally it is given that **N > K** (otherwise it would be a encoder) and **2<sup>K</sup> >= N** (otherwise the result of the encoding could not be guarantied).

![[Coder_Circut]]

## Binary Coder (Encoder)
Allows to encode **2<sup>K</sup>** inputs into **N** outputs. Only one input can be active at a time. This can be used to translate an input array into its binary number representation like for example translate button presses on a keyboard into their binary number.

## Priority Coder
Unlike with a normal coder this only allows for multiple inputs to be active with some having higher priority on the output.