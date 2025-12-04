---
tags:
  - AVS
aliases:
  - exception
  - exceptions
---
An exception is an unexpected internal event while processing a specific instruction, such as division by zero, undefined op-code or page drop. 
## Instruction Restart
Commonly instruction cannot be completed and must be restarted (redone) after taking care of the exception. This requires annulation of effects of one or more finished instructions (restoration).
### Trap
Trap is a special instruction calling system. It handles transition into a privileged mode of the kernel ([[Software]] [[Interrupt|interruption]]). 