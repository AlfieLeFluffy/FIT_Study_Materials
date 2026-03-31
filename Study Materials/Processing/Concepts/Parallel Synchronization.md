---
tags:
  - PRL
aliases:
  - parallel synchronization
sources:
  - "[[PRL_01_Parallel_Architectures.pdf]]"
---
Synchronization does not transfer data, only makes sure that required time relations between events are kept. In distributed systems such as [[Multiple Instruction Multiple Data]] this can be done either in *logical time* or in *timestamps* (tokens).
## Resources
Possible resources for synchronization are:
- Sending messages (best synchronous)
- Rendezvous (remote procedure call - RPC)
- Semaphores
- Monitors
- Barriers
## Typical Tasks
Some typical tasks for synchronization are:
- Concurrency
	- Related exclusion
	- Writers x readers
- Cooperation
	- Agreement
	- Procedure (consumer)