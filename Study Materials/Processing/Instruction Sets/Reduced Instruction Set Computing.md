---
tags:
  - INP
  - AVS
aliases:
  - RISC
---
**Reduced instruction set** that unlike [[Complete Instruction Set Computing|CISC]] implements a small amount of [[Instruction]]s, most often only elementary (atomic) operations that can be strung together to mimic complex instructions. An example of processor architecture using RISC is Apple Silicon.
## Common Properties
Common properties of RISC:
- All [[Instruction|instructions]] have a static 32 or 64 bit length.
- There is a low instruction formats, which lead to easier and quicker loading, decoding and execution in 1 cycle.
- Addressing to memory and most common [[Instruction|instructions]] are LOAD and STORE.
- Memory operands are aligned in blocks of [[Cache|cache]].
- Uses a greater number of registers.
- Most of the chip is dominated by registers.
- Processors implementing RISC have a lower energy requirements (are more efficient) and are becoming more popular.
