---
tags:
  - AVS
aliases:
  - reservation stations
  - RS
  - Tomasul's Algorithm
---
Reservation station and Tomasul's algorithm are a type of dynamic instruction planning for [[Superscalar Processor|superscalar processors]].
## Terminology
Reservation stations use some terminology and abbreviations that are good to know:
### Structure
- **PC** - [[Program Counter]]
- **FX** - Integer function unit for integer instructions
- **FP** - Instruction/Unit with floating decimal point
- **L/S** - Instruction/Unit for memory access load/store
- **B** - Unit for processing jumps, which has two parts B1 and B2
- **RF** - Register field, which include RRF (renamable registers)
- **RS** - Reservation station
- **CDB** - Central data bus
### Instruction
- **IF** - loading a group of instructions, prediction of jumps
- **ID** - decoding of instructions and renaming of registers
- **DI** - dispatching of instructions to **RS** and **[[Reorder Buffer]]**
- **EX** - sending of instructions into function units and their execution
- **WB** - updates of **RF** (ARF) depending on order in the **[[Reorder Buffer]]**
- **MW** - updates states in the D-cache (Memory Write)
## Element Format
### Instructions
Stored instructions in a reservation station have a format that includes:
- **Busy bit**
- **Operation**
- **src1** (value, tag1, valid bit V1)
- **src2** (value, tag2, valid bit V2)
- **dst** (address, tag)
- **Ready bit**
### Registers
Register in the **RF** values have a format the includes:
- **Valid bit**
- **Tag**
- **Value**
## Algoritm
The algorithm is divided into several phases that during instruction execution. These phases are:
1. **Target operand**
	- Dynamically creates a tag.
		- Writes this into **RS**.
		- Writes this into **RF**.
	- The currently contents of **RF(dst)** get invalidated $V = 0$.
	- Only the last renamed dst register will have a copy of **RS** and **RF**.
	- Previously renamed instances of this dst register still exist in **RS**.
2. **Source operands**
	- Valid values $V=1$ of the source operands from **RF** including their tags are loaded into the **RS** simultaneously with the instruction $V_{1}/V_{2} = 1$.
	- For so far invalid operands $V=0$ only the tag is loaded into into **RS**.
3. **If source operands for instruction in RS are ready**
	- Function unit is ready and $V_{1},V_{2} = 1$
	- The instruction is dispatched from **RS** into a function unit.
	- Otherwise wait until operands are ready (eliminates RAW)
4. **Function unit creates result**
	- Function unit broadcasts the resulting value over **CDB** (if it is free) together with its address and tag of the destination register.
5. **RS monitors CDB**
	- Tags of waiting instruction in **RS** are compared to the tags from **CDB**.
	- If the tags match then the value is caught and stored in the corresponding instruction in **RS**. (eliminates WAR, WAW)
6. **RF monitors CDB**
	- If the tag on **CDB** matches a tag in the **RF(dst)** then the value gets stored in parallel and the valid bit gets set to 1.
	- If the tags do not match (the register was already renamed) then the value does not appear in **RF(dst)** and is only caught in **RS**.
## Conclusion
- Instruction relation **RAW** is detected and solved by waiting in the **RS**.
	- In [[Scalar Processor|scalar processors]] this was solved by stalling of instruction after finding issues during **ID** phase, similar to INO [[Superscalar Processor|superscalar processors]].
- Instruction that create **WAR** and **WAW** conflicts:
	- Registers visible to the programmer are mapped (renamed) to elements in **RS**.
	- Conflicts WAR and WAW are better solved by explicit renaming.
- In [[Superscalar Processor|superscalar processors]] that use INO renaming does not happen.