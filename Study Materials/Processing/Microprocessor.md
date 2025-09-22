---
tags:
  - INP
  - AVS
  - to_be_finished
aliases:
  - Processor
  - CPU
---
A microprocessor is the central computing unit of a computer, which is comprised of several components, which are usually put together onto one chip.
## Microprocessor Development

| Architecture                                      | Instruction Serving | Instruction Execution             |
| ------------------------------------------------- | ------------------- | --------------------------------- |
| Subscalar [[Von Neuman Architecture\|von Neuman]] | Sequential <0,1>    | Sequential in Several Tacts       |
| Scalar ([[Pipelining]])                           | Sequential <0,1>    | Parallel with CPI>1               |
| Superscalar and VLIW                              | Parallel <0,m>      | Parallel with IPC < m             |
| Multi-core with time MT                           | 1 Core              | Multiple [[Thread]]s              |
| Multi-core with time and space MT                 | Multiple Cores      | Multiple [[Thread]]s on each core |
## Sub-scalar to Scalar
Sub-scalar processors are such that do not implement [[Pipelining|pipelining]] and thus resolve each [[Instruction|instruction]] one after another. Scalar processors that do implement [[Pipelining|pipelining]].
### Pipelining
![[Pipelining]]