Flip-flops (klopný obvod) are the simplest sequence circuits. They react in **leaps** (**skokově**, omitting the delays on their logic gates) and can moves or pass between several **discrete states**.
## Types
- **Astable** (astabilní) do not have any stable state and constantly oscillate. They can be used to generate rectangular signals or clock signals.
- **Monostable** have only one stable state. They are sequence circuits that generate a puls on start-up. They can be through of as a bowl to which can thrown one ball and can be used for timers.
- **Bistable** (flip-flop) are the most commonly used type of flip-flops and have to stable states, between which can be switched (0 -> 1, 1 -> 0). They are the base for Volatile [[Memory]], such as [[Register]], operand memory, [[Counter]], etc...
- **Schmitt's** (Schmittovy) are used to change the shape of impulses. Their basic property is # Hysteresis. Their output is dependent on the value of the input and of its original value. 

## Bistable Flip-Flops
There are many types of bistable flip-flops and here are the highlights:
### SET flip-flop
Extremely simple, but practically unusable. Once its in log. 1 it cannot be flopped back to 0. It produces a Moor's output. ![[SET_Flip-Flop]]
### R-S flip-flop (reset-set)
Setting log. 1 to the R (reset) input sets the output to log. 0.
Setting log. 1 to the S (sest) input sets the output to log. 1.
If both inputs are set to 1 then it results in a forbidden combination that previously was not able to be resolved, but today with NOR gates they will both get set to log. 0.

| R   | S   | Q<sub>n+1</sub> |
| --- | --- | --------------- |
| 0   | 0   | Q<sub>n</sub>   |
| 0   | 1   | 1               |
| 1   | 0   | 0               |
| 1   | 1   | X               |
![[R-S_Flip-Flop]]
### R-S flip-flop with enabling input (reset-set)
The same flip-flop as classical R-S, but with an additional input of C (Control, Enable), that enables the flip-flop to change state. The flip-flop state can only be changed when the input C is active, which depending on the design can be either in log. 0 or in log. 1.
![[R-S_Flip-Flop_With_Control]]
### J-K flip-flop
In this flip-flop the input **K** corresponds to **S** and input **J** corresponds to **R** and includes feedback, which eliminates the forbidden combinations. In case both inputs are in log. 1, the flip-flop toggles the current state of the output.
![[J-K_Flip-Flop]]
### T flip-flop (toggle)
This flip-flop is just the J-K flip-flop with on input instead of two.
![[T_Flip-Flop]]
### D flip-flop
It is a R-S flip-flop with one input D instead of two and negation in front of the R input.
![[D_Flip-Flop]]
### D flip-flop with enabling input
Same as D flip-flop just with an enabling (control) input.
![[D_Flip-Flop_With_Control]]

## Two-phase Bistable Flip-Flops
They are used within synchronous circuits that are driven by a clock signal (CLK). They can be either of type Master-Slave or Derivation.
- **Master-Slave** flip-flops change their output state either on while CLK is in log. 0 or log. 1. Importantly Master flip-flop is active in one phase of CLK like for example in log. 0 and Slave flip-flop is active only in the other phase of CLK like for example in log. 1. These can be done in sorts of types such as R-S, J-K, T, D, etc...
- **Derivation** flip-flops change their output state on the edge of CLK changes, so either on the rising or falling edge of the CLK signal change. 