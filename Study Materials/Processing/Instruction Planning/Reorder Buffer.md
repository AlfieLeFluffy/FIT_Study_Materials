---
tags:
  - AVS
aliases:
  - reorder buffer
  - RB
---
A **reorder buffer** is cyclical (round) buffer memory ([[Cache|cache]]) that contains memory of unfinished instructions, which is comprised of:
- Instruction state
- Preliminary/Speculative results
Instructions are inserted into the reorder buffer when dispatching into [[Reservation Stations|reservation station]]. All unfinished instructions are kept here in a FIFO queue in program order. Instructions are only dispatched further from the front of the queue, after all previous instructions are already dispatched. Writing into registers/memory can only be done once instructions leaves the reorder buffer. Reorder buffer can be also used for renaming.
## Element Format
The format of instructions stored in the reorder buffer are:
- **Instruction type**
- **Destination** address of register for storing of value.
- **Flag** keeping state of instruction.
	- Binary flag shows if instruction was finished in function unit.
	- Multibit flag can also hold additional information about the state.
- **Value** calculated by the instruction.
	- This value is not binding.
	- This field represents a set of registers **RenameRF**.
	- The binding value is inside the register.
For each dispatched instruction there is a reserved first empty place at the end of the active section of Reorder Buffer.
Reorder buffer also contains the history of multiple renaming of the same register. The oldest version of the register can already be in **ARF**, the previous can be inside the queue in the Reorder buffer and the youngest at the end.
## Uncertain Interruption
A reorder buffer is used to mitigate a [[Interrupt#Unprecise Interruption|Uncertain Interruption]]. Instructions are dispatched in program order and interruption for instructions are flagged in reorder buffer by a **special bit**. Importantly [[Microprocessor|processor]] only handles interruptions of instructions at the front of the reorder buffer. This way the instruction has not yet written its results into register and can be redone after handling the interruption, which makes it a certain interruption.