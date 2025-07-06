As a processor is a very complex circuit in which execution of an instruction is handled in different parts of the circuit it would make sense to stage these parts so that each part can work at the same time. For this the processor is divided into **stages**, with each stage handling a different stage of the instruction execution. Between each stage information should ideally flow from one to another with the clock rate, which should result in the best pipelining performance as all stages are working at the same time. The ideal number of Cycles Per Instruction (CPI) should then be 1.
## Common Stages
There are 5 common stages in this process:
- **Fetch** - loads an [[Instruction]]
- **Decode** - decodes the [[Instruction]]
- **Execute** - executes the [[Instruction]]
- **Memory Access** - read from [[Memory]]
- **Write Back** - writes into [[Memory]]

## Pipelining Ratio
Is a ration between how many cycles it would take to execute instructions separately and pipelined.

**(N * k * t) / (k + N - 1) * (t + d)**

Parameters:
- **N** - Number of instructions
- **k** - Amount of stages
- **t** - Stage Delay
- **d** - Register Delay

## Conflict (Hazards)
Conflicts are situations that are needed to be resolved during pipelining, otherwise the result of an instruction (usually a math operation) would be incorrect. Frequent conflicts can slow down the line (stall) and the line must wait for some instruction to finish before resuming. Sometimes the [[Compilator]] switches around the sequence of operations.
### Types of Conflicts
- **Structural** - the circuit does not allow two specific instructions to be executed at the same time, such as double reading from the [[Memory]].
- **Data** - An instruction requires data output from a previous instruction that was not yet finished (writing into memory). If not checked for the instruction would work with invalid register values. There are ways to mitigate this issue through **Forwarding** or **Bypassing** is an expensive, but clever solution that allows to share values between stages. We can divide data conflict further into:
	- **RAW** (Read After Write) - The second instruction is trying to read a resource before the first instruction write into it.  
	- **WAW** (Write After Write) - The second instruction is trying to write into a resource before the first instruction writes in it.
	- **WAR** (Write After Read) - Second instruction is trying to write into a resource before the first instruction reads it.
- **Control** - Jump instructions that change the value of [[Program Counter (PC)]]. For conditioned jumps  the processor does not know the address of the next instruction after the jump so it cannot fetch it so the line must stall. There are certain ways to mitigate this issue:
	- There are independent instruction that can fill out that time until the destination of the jump is known.
	- Use specialized circuits that predict the target address and can start buffering instruction ahead.

