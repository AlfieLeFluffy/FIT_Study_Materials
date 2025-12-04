---
tags:
  - INP
  - AVS
aliases:
  - Processor
  - CPU
---
A microprocessor is the central computing unit of a computer, which is comprised of several components, which are usually put together onto one chip.
## Microprocessor Development

| Architecture                                      | Instruction Serving | Instruction Execution             |
| ------------------------------------------------- | ------------------- | --------------------------------- |
| Subscalar [[Von Neuman Architecture\|von Neuman]] | Sequential <0,1>    | Sequential in Several Tacts       |
| [[Scalar Processor\|Scalar]] ([[Pipelining]])     | Sequential <0,1>    | Parallel with CPI>1               |
| [[Superscalar Processor\|Superscalar]] and VLIW   | Parallel <0,m>      | Parallel with IPC < m             |
| Multi-core with time MT                           | 1 Core              | Multiple [[Thread]]s              |
| Multi-core with time and space MT                 | Multiple Cores      | Multiple [[Thread]]s on each core |
