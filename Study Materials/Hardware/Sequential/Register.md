Registers allow to store information of a certain bit length. 
## Common Properties
- They are usually realized by **D** [[Flip-Flop]].
- These [[Flip-Flop]]s are connected to the same clock signal.
- They can have asynchronous clearing through **[[CLR]]** signal and they can have an enable (control) signal **[[CE]]**.
- Their input and output are referend to as a [[Vector]]s, D<sub>31</sub>-D<sub>0</sub> and Q<sub>31</sub>-Q<sub>0</sub> respectively.
- It is possible to write one bit at a time, but it is not commonly done so.
- Commonly registers represent some binary number, like for example 32-bit, 16-bit, 8-bit, that can enter other circuits like [[ALU]] as an [[Operand]].
- They are commonly used in construction of [[Study Materials/Automata/Types/Automata]]s to represent the current state.

## Memory Register (Latch)
Basic memory register that stores bits, usually some variation of 2<sup>N</sup> number.

## Shift Register
Synchronous circuit using [[CLK]] made out of [[Flip-Flop]]s configured in a series. In operation they move one bit of information to left or right with every [[CLK]] impuls. They have a Data in input and Data out output on the ends of the register space, arranged depending on what direction the counter should be counting in.
There exists several types and common uses for shift registers such as:
- **Master-Slave [[Serial Peripheral Interface (SPI)]]** for MISO and MOSI
- Data buffer for [[Universal Asynchronous Reciever-Transmiter (UART)]] before being sent
- Data buffer for [[Universal Asynchronous Reciever-Transmiter (UART)]] for receiving data
- Storing [[Operand]] values
- Sequential [[Adders]]

## Diagram of Common Registers
![[Registers_Diagram]]
