---
tags:
  - IMP
  - AVS
  - to_be_finished
aliases:
  - interrupt
  - interrupts
---
An interrupt (or its servicing) is a mechanism, that allows the [[Microprocessor|processor]] to create to events that are generated asynchronously. These interrupts can for example be generated through pressing a key on a key board, moving a mouse, etc. Interrupts can also be generated from inside the processor like for example division by zero. 
## Interrupt Handling
A sequence of actions is performed once an interrupt is detected:
1. Peripheral device generates an interrupt through an electric impuls in the Interrupt Controller.
2. Interrupt Controller identifies the interruption and notifies a processor.
3. Once the processor is in a state where it can handle the interruption (finishes an [[Instruction]]) it asks the Interrupt Controller for the highest priority non-maskable interruption it has and begins its routine.
4. Processor save the current state of the currently running process on the [[Stack]].
5. Based on the [[Vector]] of interruption the processor chooses the handling routine, finds it and executes it.
6. After finishing the handling routine the processor restores and continues in the interrupted process.
## Properties
- **Priority** - Interruption priority indicates in which order interrupts should be handled in. 
- **Masking** - Some interruption can be masked, in which case the process will ignore them.
## Unprecise Interruption
An issue when parallelly processed operations end in different order then in the program and one of them (usually the longer one) ends in an interruption, but the other instruction already rewrote the register.
A way to mitigate this issue is to hold the result of the shorter instruction in temporary memory and only rewrite the register after the longer instruction finished and rewrote its register. This can be done by only allowing rewriting from the front of the [[Reorder Buffer|reorder buffer]].