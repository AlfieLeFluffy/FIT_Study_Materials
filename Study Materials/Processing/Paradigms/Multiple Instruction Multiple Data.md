---
tags:
  - AVS
  - PRL
aliases:
  - MIMD
sources:
  - "[[PRL_01_Parallel_Architectures.pdf]]"
---
Unlike other members of the [[Flynn's Classification]] this processing paradigma can works with multiple instructions on multiple data at the same time, usually by using several processors in parallel.
## Communication
[[Parallel Communication|Parallel communication]] in MIMD is handle through either **shared memory** or **messaging** and depends on the context:
- **Multitasking**
	- 1 [[Microprocessor|CPU]]
	- Switching context
	- Virtual processors
	- *Messaging* is simulated in SW
	- *Shared memory* can normally work
- **Shared memory**
	- Multiple [[Microprocessor|CPUs]]
	- [[Cache]]
	- Closely bound
	- Fighting over bus
	- *Messaging* is simulated in SW, HW
	- *Shared memory* can normally work
- **Virtual share memory**
	- Multiple [[Microprocessor|CPUs]]
	- All [[Cache|cache]]
	- Merging/connecting cheches done through communications channels
	- Front-end is pretending to be one addressing space
	- *Messaging* is simulated in SW, HW
	- *Shared memory* is simulated in HW
- **Messaging**
	- Freely bound architecture
	- Computer networks
	- Interconnected only processors
	- *Messaging* can work normally
	- *Shared memory* is simulated in SW