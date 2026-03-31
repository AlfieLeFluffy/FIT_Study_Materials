---
tags:
  - PRL
  - to_be_finished
aliases:
  - dataflow
  - dataflow architecture
  - dataflow graph
  - Dataflow Graph
sources:
  - "[[PRL_01_Parallel_Architectures.pdf]]"
---
Dataflow architecture is a [[Non-Von Neuman Architecture|non-Von Neuman architecture]] (doesn't not have a program or PC) and computers/renders interpretation of dataflow [[Graph|graph]]. We can take a program that can be converted into a dataflow graph, which can subsequently be evaluated by a dataflow computer/architecture into an graph interpretation.
## Dataflow Graph
A dataflow [[Graph|graph]] has special vertices (nodes) that have special meaning, inputs and outputs. Each node types simulates mathematical, logic operation or is used for synchronization.
![[Dataflow_Graph_Node.excalidraw.svg|300]]

### Node Types
There are many types of dataflow graph nodes, but the most common are duplication of input, basic mathematical operations, such as +,-,>,<, logic gate operations, such as AND, NOT, OR, and synchronization operations, such as BARIERA.
## Dataflow Processors
There are two main types of dataflow processor architectures, **static** and **dynamic**, each working slightly differently from each other.
### Static
![[Dataflow_Processor_Static.excalidraw.svg|450]]
### Dynamic
![[Dataflow_Processor_Dynamic.excalidraw.svg|450]]
## Dataflow Languages
The main requirement from a dataflow language is a **single assignment rule**, which means that a variable can appear on the left side of assignment only once (inside the code area). Examples of dataflow languages are VAL, ID, LUCID.
A **dataflow program** is a compiled/translated into a **dataflow graph** and then can be executed on a dataflow computer/processor.