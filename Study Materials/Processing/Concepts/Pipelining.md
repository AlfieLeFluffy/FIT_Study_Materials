---
tags:
  - INP
  - AVS
aliases:
  - pipelining
---
As a [[Microprocessor|processor]] is a very complex circuit in which execution of an instruction is handled in different parts of the circuit it would make sense to stage these parts so that each part can work at the same time. For this the [[Microprocessor|processor]] is divided into **levels** (stages), with each stage handling a different stage of the instruction execution. Between each stage information should ideally flow from one to another with the clock rate, which should result in the best pipelining performance as all stages are working at the same time. The ideal number of Cycles Per Instruction (CPI) should then be 1.
## Common Stages
There are 5 common stages in this process mainly seen in [[Reduced Instruction Set Computing|RISC]] processors:
- **IF** - *Instruction Fetch* loads an [[Instruction]].
- **ID** - *Instruction Decode* decodes the [[Instruction]] and loads register operands.
- **EX** - *Execute* executes the [[Instruction]].
- **MA / CA** - *Memory Access* accesses data from [[Cache|cache]].
- **WB** - *Write Back* writes the resulting value into a target [[Register|register]].
## Pipelining Accelaration
A pipeline acceleration can be expressed as a ration between how many cycles it would take to execute instructions separately and pipelined.
$$\frac{N \times k \times t_{s}}{(N + k - 1)\times(t_{s} + t_{d})}$$
Parameters:
- $N$ - Number of instructions
- $k$ - Amount of stages
- $t_{s}$ - Stage Delay
- $t_d$ - Register Delay
## Ideal Pipeline
An ideal pipeline has several properties such as:
- All objects passthrough the same levels, meaning there is an uniform length of instructions.
- No pair of levels share the same [[Hardware]] resources, meaning that the time of passing through a level is always the same.
- Timing of objects entering into the pipeline is not influenced by objects in different levels.
These properties generally apply for many other pipelines, but unfortunately [[Instruction|instructions]] are commonly dependent on each other. These dependencies can be resolved in [[Software]] by things such as [[Compiler|compiler]] making changes to the program or through [[Hardware]] that can make operations that resolve these dependencies on the fly.
## Pipeline Expectations
These are some expectations that a pipeline and things connected to it must follow or do.
### Prerequisitise
There are several prerequisites a pipeline expects to work properly, these are:
- An **uninterrupted access** to data and code.
- Both data and code are processed in **similar ways**.
- Processing must be **divisible into a sequence of independent steps**.
- Each step can be resolved into a **different level of the pipeline**.
- The **time required** to process one level **should be roughly the equal** as the rest.
### Influencing Dependencies
Some things have influence over the overall reachable acceleration, these are:
- **Necessary timeouts** (disengagement) during processing influenced by **relations**.
- The **start-up and stopping** of the pipelined processing for a finite amount of N processed elements.
- The delay of **separating** [[Register|registers]].
## Conflict (Hazards)
Conflicts are situations that need to be resolved during pipelining, otherwise the result of an [[Instruction|instructions]] would be incorrect. Frequent conflicts can slow down the pipeline (stall) and the line must wait for some instruction to finish before resuming.
### Types of Conflicts
There are three main types of conflicts:
#### Structural
The circuit does not allow two specific instructions to be executed at the same time, such as double reading from the [[Memory]].
#### Data
An [[Instruction|instruction]] requires an output from a previous instruction that was not yet finished. If these issues would not be detected and resolved the instruction would work with invalid register values, which would result in a domino effect where each following instruction could work with the invalid result. 
We can divide data conflict further into:
- **True Dependencies**:
	- **RAW** (Read After Write) - The second instruction is trying to read a resource before the first instruction write into it.
		- Solutions to such conflicts can be *stalling the pipeline* until the result is known, *forwarding/bypassing* of data between stages, etc.
- **False Dependencies**:
	- **WAW** (Write After Write) - The second instruction is trying to write into a resource before the first instruction writes in it.
		- A solution can be *renaming*.
	- **WAR** (Write After Read) - The second instruction is trying to write into a resource before the first instruction reads it.
		- A solution can be *renaming*.
#### Control
Control conflicts occur when a jump instructions that change the value of the [[Program Counter]]. On average every 6.-9. [[Instruction|instruction]] is a jump. For conditioned jumps the [[Microprocessor|processor]] does not know the address of the next instruction after the jump so it cannot fetch it so the line must stall, everything that was executed after the jump instruction must be flushed and usually there is a fine of several cycles. 
There are certain ways to mitigate this issue:
- For unconditional jumps the address is already known after it is calculated in **EX** and in **MA** it can overwrite the [[Program Counter|PC]]. This result in a *3 cycle fine*.
- This can be improved by adding a new separate counter that calculates the address during **ID** and reduces the *fine to only 1 cycle*.
- For conditional jumps this same counter can be used to calculate the address head of time and the condition can be detected if it is zero in **ID**. This can result in *1 or 0 cycle fine*.
- Conditional jumps can be *fined additional cycles* depending on the instructions calculating the condition.
### Compiler Assistence
There are several ways the [[Compiler|compiler]] can help with pipelined processing, such as:
- **Renaming [[Register|registers]]**, which gets rid of false dependencies.
- **Filling empty cycles** with useful instructions.
- **Reordering of instructions** without changing the semantics of the program by checking the delay between operations or speculative tossing (reordering) of instructions.
- **Unpacking of loops**
- **[[Software]] pipelining of loops** in a program or combining their unpacking.
The compiler knows the latency of operations and in-between operations. 