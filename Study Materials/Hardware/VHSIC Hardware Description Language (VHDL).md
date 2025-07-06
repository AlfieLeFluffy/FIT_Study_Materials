VHDL uses one of three ways to describe a hardware implementation that can then for example be simulated. In the real world these three ways are usually combined to describe logic through several means. These descriptions can then be synthetized (sort of compiled) for a given technology such as [[Field Programmable Gate Array (FPGA)]] or [[Application Specific Integrated Circuit (ASIC)]].
## Types
### Structural
In structural description we **define entities** (like a [[Adders#Half Adder|Half Adder]]) through combining components (like AND and XOR gates), that realize the logic of the entity. The components themselves can be entities described on a lower level of abstraction. Structural description allows to decompose complex system into less complex components that can be designed separately. The designer in this description style has control over how the final circuit will look.
```
library ieee;
use ieee.sdt_logic_ii64.all;

entity half_adder is
	port (a, b: in std_logic;
	sum, carry_out: out std_logic);
end half_adder;

architecture structure of half_adder is

	component xor_gate
		port (i1, i2: in std_logic;
		o1: out std_logic);
	end component;
	
	component and_gate
		port (i1, i2: in std_logic;
		o1: out std_logic);
	end component;

begin
	u1: xor_gate port map (i1 => a, i2 => b, o1=> sum);
	u2: and_gate port map (i1 => a, i2 => b, o1=> carry_out);
end structure;
```
### Behavioural
Describes the behaviour of a system/function/block algorithmically. It is the most abstract description. From behaviour description is not completely clear what the implementation on the logic gate level will look like. Its elements contain one or more processes that happen in parallel. Each process is happening in sequence. In the process the output is dependent on the input values.
```
library ieee;
use ieee.sdt_logic_ii64.all;

entity half_adder is
	port (a, b: in std_logic;
	sum, carry_out: out std_logic);
end half_adder;

architecture behvaiour of half_adder is
	begin
		ha: process (a, b)
		begin
			if a = '1' then
				sum <= not b;
				carry_out <= b;
			else
				sum <= b;
				carry_out <= '0'
			end if;
		end process ha;
end behvaiour;
```
### Dataflow
The dataflow descriptions are used to model system on the basis of how the data in them flows. This way uses description of implementation of logic gates and describes systems/elements in one or more connected parallel signals. 
```
library ieee;
use ieee.sdt_logic_ii64.all;

entity half_adder is
	port (a, b: in std_logic;
	sum, carry_out: out std_logic);
end half_adder;

architecture dataflow of half_adder is
	begin
	sum <= a xor b;
	carry_out <= a and b;
end dataflow;
```