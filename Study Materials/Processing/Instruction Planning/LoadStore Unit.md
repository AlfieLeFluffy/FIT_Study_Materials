---
tags:
  - AVS
aliases:
  - Load/Store Unit
  - load/store unit
  - LSU
---
A Load/Stone unit is comprised of three stages (without outage):
1. Address generation ([[Adders|adder]])
2. Address translation (DTLB)
3. Reading from [[Cache|cache]] (writing is not seen)
Translation of an address in TLB and access to the *physically addressed (P/P) cache* usually happens in series, which means the delay gets linearly summed. In cache with *virtual indexing (V/V and V/P) cache* it is possible to access the TLB and cache simultaneously, which means overlapping delays.
## Memory Access Order
Between instructions Load and Store also exist data relations, similarly to registers. These relations can create issues such as:
- **RAW**, **WAR** and **WAW**
- Cannot be detected sooner then when the addresses are calculated of the memory operands.
- These relations must be respected, so the semantics of the program can be kept.
### Instruction Order
Instructions Load and Store can be either done in program order, which can be slow or they can be under certain circumstances done out-of-order (OOO). These include:
- **RPR** - Read Pass Read
- **RPW** - Read Pass Write
- **WPR** - Write Pass Read
- **WPW** - Write Pass Write
### Read Pass Write
A read instruction can pass write instruction. An OOO [[Superscalar Processor|superscalar processor]] can in essence do [[Hardware]] loop decomposition. A new load instruction can bypass and current store instruction; the iterations of the loop can partially overlap.
RPW is one of the main sources of better performance, loading can be at the start of a loop with depending instructions either:
- Load from address Z can bypass store with a **different address** X, that has not started yet.
- Load gets data from not yet finished instruction store with the **same address** X (forwarding).
A technique using RPW requires dynamic differentiation of addresses. $address(R)\neq address(W)$. Depending on that it can either:
- **Addresses do not match**: There is not RAW conflict and Load(R) does not wait for Store(W) and bypasses it, reads data from the D-[[Cache|cache]] into the destination register.
- **Addresses match**: Load(R) loads data into the destination register (RRF or ROB) from the waiting unfinished store from the store buffer.
- **Doesn't know**: Stalls (waits) or speculates that the address do not match.
## Store Buffer
Store buffer holds all unfinished writes before **WB** phase (stage). An element in the store buffer is allocated into the store buffer during decoding (**DI**). If the store buffer is full, it must wait. The Store instruction addresses are in the buffer in program order. New Load instructions are checked against the waiting addresses of Store for a match.
### State Bits
Each element in the buffer has state bits that indicate:
- **Available** - an element is free and available to be used.
- **Adr only** - address is already in the buffer, but the data not yet.
- **Ready** - address and data are already in the buffer.
- **Completed** - validated writes, waiting for the Store instruction to be at the front of the [[Reorder Buffer|reorder buffer]].
## Load Buffer
If some addresses for Store are not known yet, it can speculated, if they will differ from the addresses in Load. To check the speculation:
- Addresses of newly finished speculative loads saved into a Load Buffer.
- Each completed Store instruction must verify that it does not have an address that matches with an element in the Load Buffer.
	- If there is a match, the instruction Load and every instruction after that one needs to be cancelled and redone.
	- If the is no match, the Store instruction is done and a rewrite of Load data from RRF into ARF is done.
- In terminology x86 it is called Load Queue.
## Relaxed Memory Consistency
Sequence consistency, which keeps order in access into memory, is not in modern time interesting. It is a an obstacle of modern [[Hardware|hardware]] and optimizing [[Compiler|compilers]]. RPW skipping is one way to relax accessing into memory, even through for performance is not as interesting. There exists a series of other more relaxed models with completely free order of reading and writing into memory. Modern [[Microprocessor|processors]] use relaxed memory consistency, where read and writing can freely bypass each other if it does not influence the correctness of the program.
### Impacts
There some impacts that relaxed memory consistency has, such as:
- Better performance.
- Easier [[Hardware]] implementation.
- It is left up to the programmer to specify instructions that must be ordered correctly.
- All remaining instructions  can be done out-of-order.
On the higher level the programmer must use synchronization commands to define areas that require load/store instructions in-order, such as:
- Directive **flush** in *OpenMP*.
- Variable **volatile**, etc.
The main disadvantage of relaxed models is putting more burden on the programmer and can result in more complex errors.
### Barriers and Fences
**Fence** is a special memory instructions that prevents reordering of load/store instructions where it is necessary. All instructions load/store in the program before the **fence** must finish and only after fence can begin more. In a sequence WFR cannot happen a RPW. These instruction can either do:
- **Full stop**
- **Partial stop** for either read or write
- **One way stop** has two instructions **acquire** that stops moving load/store up and **release** that stop moving load/store lower.
### Possible Data Flow Optimalization
Some ways to improve data flow over memory:
- Sequential writes at the front of the [[Reorder Buffer|reorder buffer]] to the same D-[[Cache|cache]] can be done at the same time.
- More important is to optimize reading over writing, because they can prevent further calculations. Reading appears twice as often as writing and the appearance of page drops is about the same. 
- During page drop during reading in common blocking [[Cache|cache]] L1 the pipeline (function unit) L will stall and no further instructions are dispatched until the drop is resolved.
- The Load/Store unit that allows only one read or write in one cycle is rather limiting for a group of L instructions. That is the reason multiple L/S units are used, non-blocking cache or cheaper composite cache is used.
- Advantages:
	- Other accesses after dropping during reading that do not require data from the drop are not blocked.
	- Allow processing of several simultaneous page drops and hits.
	- A lot of L1 and L2 caches are non-blocking D-[[Cache|caches]].