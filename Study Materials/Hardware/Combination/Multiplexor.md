A multiplexor is a [[Combination Circuit]] that can choose one input of **2<sup>N</sup>** inputs with **N** control inputs. 
	Essentially if you have 4 inputs you can use 2 control inputs to choose one of those 4 inputs. This also means that if you only care about moving around only one of those inputs you can instead of creating all 4 wires only create 3 wires. One wire is for the input and the other two are for telling the other side of which of the four inputs this one is. This is not as apparent on a small scale as this one, but for 8 input you only have to carry 4 wires, for 16 you only need 5 wires, and so on.

Multiplexors are created with logic gates and can be configured in many ways and technically do not have a limit to their size.

- 2-1 Multiplexor created with NOT, AND and OR: ![[2_To_1_Multiplexor_NOT_AND_OR]]
- 2-1 Multiplexor created with only a NAND: ![[2_To_1_Multiplexor_NAND]]
- 4-1 Multiplexor created with NOT, AND and OR: ![[4_To_1_Multiplexor_NOT_AND_OR]]
- 4-1 Multiplexor created in diagram form: ![[4_To_1_Multiplexor_Diagram]]