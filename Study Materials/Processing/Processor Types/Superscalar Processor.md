---
tags:
  - AVS
  - to_be_finished
aliases:
  - superscalar processor
---
## Scalar to Superscalar
Superscalar processors use the same [[Pipelining]] technology as [[Scalar Processor]], but expand it by creating multiple pipelines that can work simultaneously. This means that during one cycle there are multiple pipelines, each pipeline executing several levels (stages) at once.
## Structure
The processor and its pipelines are divided into two sections:
### Front-end
Front-end corresponds to levels (stages) **IF** and **ID**. It's responsibilities are:
- Loads and decodes several instruction at the same time. The number of instruction changes dynamically.
- A superscalar processor with **m** paths can send up to **m** instruction into **function units** (pipelines) in one cycle.
### Back-end
Back-end corresponds to levels (stages) **EX**, **MA** and **WB**. It is responsible for:
- Execution and storing of results of multiple instructions simultaneously.
- Some levels (stages) are divided further into sub-levels (sub-stages).
- For an amount of **functional units** (pipelines) **m**, the amount of connecting paths grows as **m^2**.
## Types
Superscalar processors can be divided into types by the **way instructions leaving front-end**
- **In sequence** of a program (in-order, INO), after resolving conflicts, which is easy to do in [[Hardware]].
- **Out of sequence** of a program (out-of-order, OOO). All false dependencies are resolved by renaming in [[Hardware]], **RAW conflicts** are solved by stalling for unfinished instructions. Writing back of results in correct sequence is done through a **[[Reorder Buffer]] (ROB)**.
### Examples
Examples of processors implementing one of the types:
- **INO** are usually the first superscalar processors created, such as Pentium, DEC Alpha 21164, but also even newer processors, such as IBM Power6, Intel Atom, ARM or Intel Xeon Phi.
- **OOO** can be processors such as Intel P6, Pentium4, Intel Core/Rocket Lake/ Zen.
## Characteristics
Some of the main characteristics of superscalar processors are:
- **Parallel Pipelines** (INO, OOO) 
	- Uses both time and space parallelism such as parallel loading, decoding and sending of multiple instruction in front-end and their parallel execution and finalization.
- **Renaming of registers** in [[Hardware]] (OOO) 
	- Removes false dependencies.
- **Dynamic planning of instructions out-of-order** (OOO) 
	- After decoding instructions wait until their operands are created. Once all operands are prepared, the instruction is executed.
	- Instruction, including its access to memory, are executed in a different order then in the program.
- **[[Reorder Buffer]]** (OOO)
	- The level (stage) **WB** uses sorting memory to ensure that storing of results is done in order set out by the original program.
- **Speculative instruction execution** (OOO)
	- Speculation, that a jump will result depending on prediction or that data loaded ahead of time are not going to change.
## Dynamic Instruction Planning
Instructions are sent to a **function unit** and executed out-of-order of the original program, if there are **no conflicts** between them and **function units are free**.
There are two main systems/algorithms that create these instructions plans:
- **ScoreBoarding** also known as Thornton's algorithm developed in 1964.
	- Registers all conflicts (RAW, WAW, WAR) in a table of unfinished instructions and keeps their **score**.
	- **ScoreBoard** sends instructions to execution only if all existing conflicts with other instructions in the ScoreBoard are resolved.
	- **ScoreBoarding** doesn't do any **register renaming**.
- **Reservation Station** also known as Tomasul's algorithm was developed in 1967.
	- Conflicts WAW and WAR are solved through renaming.
	- **Reservation station** (buffers) allow for delaying of waiting instruction a working ahead on other instructions, which resolves RAW.
	- There can be different tiers of **reservation stations RS** from the *central RS* (instruction window), *individual RS* for functional unit to *group RS* for a group of functional units.
### ScoreBoarding
![[ScoreBoarding]]
### Reservation Stations
![[Reservation Stations]]
## Reorder Buffer
![[Reorder Buffer]]
## Register Optimalization
Renaming registers in the simple already exists in [[Reservation Stations|reservation stations]], but it has some issues such as the amount of elements in the reservation station is limited and the amount of registers that can be renamed in one cycle is also limited. 
While processing 4 and more instructions in one cycle there might be the need to rename several registers in one cycle or one register needs to be renamed multiple times in one cycle.
### Solutions
Some [[Hardware]] solutions to this problem are:
- Renaming registers using the [[Reorder Buffer|reorder buffer]]:
	- One ore more results of completed instructions from the front of the reorder buffer are moved in each cycle at once into the **ARF**.
- Renaming using a set of registers for renaming called **Rename Register File RRF** with multiple gates:
	- **RRF** contains validated and speculative results.
	- **RRF** can be either separated from the **ARF** or monolithic (integrated with **ARF**). 
## Load/Store Unit
![[LoadStore Unit]]
