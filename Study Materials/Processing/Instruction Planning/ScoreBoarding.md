---
tags:
  - AVS
aliases:
  - scoreboarding
  - Score Boarding
  - score boarding
  - Thornton's algorithm
---
As the name implies, **ScoreBoarding** uses a table (board), into which it enters instructions, their scores and further works with them inside this table.
## Element Format
One element inside the table has a format that includes:
- **State** of instruction (send to function unit, loading operands, finished)
- **State of function unit** (is it busy)
- **Operation** of the function unit
- **Destination** address of target register
- **Source1** address of the first source register.
- Bit **V1** is a validification bit of the first source.
- **Source2** address of the second source register.
- Bit **V2** is a validification bit of the second source.
Validification bit indicates if the source is valid and can be used in the instruction, or if it is non-valid which means that it is currently in use by other instructions ahead.
## Algorithm
The algorithm is divided into several phases depending on the level (stage) of processing and the Front-end and Back-end division.
1. **Pre-processing of new instruction** is done within the Front-end and represents the level (stage) **ID**.
	1. Reservation of target register.
		- If the register is **valid** $V=1$, it gets rewritten to $V=0$ and the element is written into the score board.
		- If the register is already **non-valid** $V=0$ then some other instruction is currently generating an output into it. The algorithm stalls until the previous instructions is done.
	2. Sending the instruction.
		- If both **source operands** are **valid** $V_{1},V_{2} = 1$.
			- Send instruction **op-code** to a function unit.
			- Send addresses of **Source1** and **Source2** into the **Register Field** and then their values into the **Function Unit**.
			- **Zero the V1 and V2** validification bits.
			- Change the state of the instruction to **Operands Loaded**.
		- If either **operand** is **non-valid** then stall until it is.
2. **Instruction execution**
	1. The result and **Destination** register address appears on the output of **function unit**.
3. **Writing back results into registers** which represents the level (stage) **WB**.
	1. If the Destination result matches either Source1 or Source2 in some instruction inside the Score Board with the validification bit $V_{1}=1$ or $V_{2}=1$ (valid and not yet used).
		- The write back into the register field on address Destination must be held back, even if the register is reserved $V=0$.
		- The current contents of the register field on address Destination was yet not read by some waiting instruction.
	2. If the relevant validification bits are zeroed $V_{1},V_{2} = 0$
		- The result is written into the register field on address Destination and the validification bit is set to $V=1$.
		- The algorithm searches the Score Board and changes the $V_{1}$ and $V_{2}$ to 1 for each element in the Score Board where we were waiting for the result of this operation.
## Conclusion
Both true and false conflicts are solved solely through stalling.