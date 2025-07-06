FPGA is a programable gate array that is a compromise between a fully [[Hardware (HW)]] solution such as [[Application Specific Integrated Circuit (ASIC)]], which quicker and more efficient and a fully [[Software (SW)]] solution, which has the most flexibility.
## Structure
It is created with:
- **Configurable Logic Blocks (CLBs)** that can be programmed with logic functions that are realized with [[Hardware (HW)]]. The blocks are comprised of several components that can together form one **CLB** or a **slice**. **CLB** can be create through multiple **slices**. These components are:
	- **Look Up Table (LUT)** is a **2<sup>N</sup>** bit [[Register]] that contains outputs (outcomes, function values) of a combination logic of **N** variables. This [[Register]] is a volatile [[Memory]] so these values have to stored in some non-volitele [[Memory]] and then configured during start-up.
	- **2<sup>N</sup>-1 Multiplexor** that chooses which of the LUT entry (bit) should be outputted depending on N input variables.
	- A [[Flip-Flop#D flip-flop|D Flip-Flop]] that stores the output as an option for turning the CLB into a [[Sequence Logic Circuit]].
	- **2-1 Multiplexor** that chooses if the CLB works as a [[Combination Circuit]] or a [[Sequence Logic Circuit]].
- **Programable Interconnects** that allow for connections between CLBs. They are implemented in columns and rows where in places they cross they can be programmed to connect (switch).
- **Programable I/O Blocks** are used to connect the CLBs with external components using FPGA chip pins.
- **Embedded blocks** can be used for additional functionality and for example are additional [[Memory]], [[Combination Circuit]]s, Ethernet...
## Design Steps Using FPGA
To design an application using FPGA, the Top-Down system design is commonly used. It starts with the description of the entire problem and ends with the design plans with full extent of details of its parts. This approach is also called **decomposition**. On every level of this plan the right functionality must be verified. With decomposition the result become simply realizable components such as [[Combination Circuit]]s, [[Register]]s, [[Counter]]s which can be described in [[VHSIC Hardware Description Language (VHDL)]] or Verilog. For example a system that can be created this way is image recognition.
## Design Steps Using Register Transfers (RT)
The design should be split into several sections:
- **Description of Circuits as a General [[Study Materials/Automata/Types/Automata]].** The SM should describe all the states of the circuit , but does not resolve configuration of control, input or output signals.
- **Creation of Data Paths.** Data paths resolve data manipulations depending on the control from the General SM.
- **Identification of Signals for Data Path Control.** Definition of signals that are necessary for connecting the data paths to the control block.
- **Design of the Control State Machine.** Conversion of the General SM into a [[Study Materials/Automata/Types/Automata#Mealy's SM|Mealy's State Machine]] or a [[Study Materials/Automata/Types/Automata#Moore's SM|Moore's State Machine]] that control the data paths. 