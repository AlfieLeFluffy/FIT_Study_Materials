Decoder transforms (decodes) encouded information from **N** inputs to **K** outputs based upon a combination table. It is complimentary circuit for the [[Coder]]. 
Generally it is given that **N < K** (otherwise it would be a decoder).

![[Decoder_Circut]]

## Binary decoder (Decoder)
Allows to decode **N** inputs into **2<sup>K</sup>** outputs. Unlike with encoder, any number of inputs can be active and will only produce one output. This can be used to turn binary numbers representations into separate outputs.