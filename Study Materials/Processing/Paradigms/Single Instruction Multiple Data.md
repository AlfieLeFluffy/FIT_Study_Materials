---
tags:
  - AVS
  - PRL
aliases:
  - SIMD
sources:
  - "[[AVS_05_Data_Paralelism_SIMD.pdf]]"
  - "[[PRL_01_Parallel_Architectures.pdf]]"
---
The basic idea of SIMD is to process multiple data inputs in a single cycle by aligning said data into vectors that can done at the same time. These operations are done through vector processors or vector units and is usually used for working with information in arrays of single data type. Initially these units were mainly used in GPUs, but today they are a common part of the processor architecture.
## Characteristics
Some advantages are:
- Simpler then [[Multiple Instruction Multiple Data|MIMD]]
- Lower [[Memory|memory]] requirements
- Only one instruction flow and synchronization simplifies programs
- Lower required orchestration between processes
- Quicker communication between processors then [[Multiple Instruction Multiple Data|MIMD]]
	- Lower latency
	- Lower orchestration
Some disadvantages are:
- Not every problems can be done through data paralysation
- Less efficient with higher number of conditioned jumps
- Not suitable for a lower amount of processors
## Multiple SIMD
MSIMD is a variation of the SIMD architecture that uses groups of independent processors. These groups are then dynamically allocated.
