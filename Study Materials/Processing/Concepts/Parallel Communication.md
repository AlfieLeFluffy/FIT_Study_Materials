---
tags:
  - PRL
aliases:
  - parallel communication
sources:
  - "[[PRL_01_Parallel_Architectures.pdf]]"
---
Interactions and data sharing between actors in parallel architectures can be done in several ways, the two main ideas are **Shared Memory** and **Messaging**.
## Characteristics
Characteristics of each approach are: 
### Shared memory
- Either *true* or *simulated*
- Fighting over bus, cache, local links
- Solving conflicts during write
- Difficult to use during synchronization
- All processors have access to a shared memory space.
- Solution of **simultaneous access** to one memory cell is either:
	- Exclusive-Read, Exclusive-Write (**EREW**)
	- Concurrent-Read, Exclusive-Write (**CREW**)
	- Exclusive-Read, Concurrent-Write (**ERCW**)
	- Concurrent-Read, Concurrent-Write (**CRCW**)
### Messaging
- *Channels*
	- *Synchronous* or *asynchronous* (capacity)
	- *One-way* or *two-way* (ACK)
- Calling remote procedures (RPC)
- Broadcasting
	- Intentional sending messages to all
	- Sending to all processes
	- Flooding
- Each processor has their own addressing space.
- Processors have their own memory (cache), which is updated between them through messages.
## Broadcast
