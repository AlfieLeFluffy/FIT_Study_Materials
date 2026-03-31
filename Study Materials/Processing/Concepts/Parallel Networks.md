---
tags:
  - PRL
aliases:
  - parallel networks
sources:
  - "[[PRL_01_Parallel_Architectures.pdf]]"
---
Interconnecting networks are used to organize communication and algorithms in [[Parallel Architectures|parallel architectures]] and [[Parallel Communication|parallel communication]]. They can be used to interconnect processors with *shared memory* or *processors themselves*. These networks are represented through [[Graph|graphs]] and inherit some characteristics.
## Types
There are four main types, which are:
- **Static**
- **Dynamic**
- **Shared** (busses)
- **Switched**
The characteristics of each network influences the suitability of individual types of algorithms and affects effectivity of data flow.
## Characteristics
Some of the shared characteristics between types of networks are:
- **Diameter** is the biggest distance from the shortest distances between pair of nodes.
- **Bisection width** is the minimal amount of edges that interconnect two halves of the networks with nearly equal amounts of processors.
- **Arc connectivity** is the minimal amount of edges that is needed to be removed to divide the network into more subnetworks and is related to the degree of nodes.
- **Network size** is the amount of nodes in the network.
- **Cost** is the amount of edges in the network.
## Static Networks
All nodes within these networks are processors. Channels are connections between nodes. Static networks are used in architectures without share memory.
### Designs
Designs of static networks are:
- **Complete interconnection**
	- All nodes in the network are connected.
	- *Diametr* $= 1$
	- *Arc connectivity* $= p-1$
	- *Bisection width* $=p^2/4$
- **Star**
	- All nodes are only connect to one central node.
	- *Diametr* $= 2$
	- *Arc connectivity* $= 1$
	- *Bisection width* $=(p-1)/2$
- **k-n cube**
	- A Carthusian multiplication of *n* linear array with *k* nodes. An example of which can be for example a hypercube, torus, circle, etc.
	- For $k=2$:
		- *Network size* $= 2^n$
		- *Diametr* $= n$
		- *Arc connectivity* $= n$
		- *Bisection width* $=2^{n-1}$
	- For **grid**:
		- *Network size* $= k^n$
		- *Diametr* $= n(k-1)$
		- *Arc connectivity* $= 2n$
		- *Bisection width* $=k^{n-1}$
	- For **one-way torus**:
		- *Network size* $= k^n$
		- *Diametr* $= n(k-1)$
		- *Arc connectivity* $= 2n$
		- *Bisection width* $=k^{n-1}$
	- For **two-way torus**:
		- *Network size* $= k^n$
		- *Diametr* $= n[k-1]$
		- *Arc connectivity* $= 4n$
		- *Bisection width* $=2k^{n-1}$
- **Ring**
	- A ring of $k$ nodes is a $k$-sized one-way torus.
- **Chordal Ring**
	- A chordal ring is a ring with connections with distance of $I$
- **d-ar Tree**
	- A [[Tree|tree]] where each node does not have more then $d$ children. Usually it is a binary tree with $d=2$.
	- *Diametr* $= 2h$, where $h$ is the tree depth
	- *Arc connectivity* $= 1$
	- *Bisection width* $=1$
## Dynamic Networks
Nodes are either processors, memory cells or switches. Usually used for implementation of architecture with shared memory. Common designs are *busses*, *crossbars* or *fat trees*.
These networks can be *non-blocking* (any two free nodes can be interconnected), *blocking* (cannot simultaneously connect any two nodes), or *configurable* (any connection can be changed to resolve conflicts).
### Dynamic Designs
Some of the above mentioned designs are:
- **Crossbar** (Cross Switch)
	- All processors are arranged in a grid. Connection paths can be created through this grid dynamically. Each processors practically behaves as a switch that can redirect communication.
	- Some processors ($p>m$) do not have access to memory.
	- *Cost* $=\Omega(p)$
	- *Permeability* $=O(p)$
	- *Non-blocking*
	- *Diametr* $= 1$
	- *Arc connectivity* $= 1$
	- *Bisection width* $=p$
- **Fat Tree**
	- Solves a problem with static trees of higher loads closer to the tree root.
	- Dynamic selection of channels for communication.
- **Shuffle and Exchange**
	- Works with node IDs.
	- *Shuffle* updates an ID with a *left shift*.
	- *Exchange* updates an ID by *inverting the last bit*.
- [[Bus]]
	- Usually involves a shared component/resource (memory), which is difficult to scale correctly, but can have a higher permeability if additional local cache is inserted between the bus and each processor.
	- *Cost* $=\Omega(p)$
	- *Permeability* $=O(1)$
	- *Diametr* $= 1$
### Switched Designs
Switched designs are based on switches, in which unlike in crossbars, data flows through switches and not nodes. Switches relay inputs onto one or more outputs. Realization can be physical through [[Multiplexor|multiplexors]] and [[Demultiplexor|demultiplexors]] with buffers in case of conflicts.
Examples of these networks are:
- **Multistage Indirect Networks**
	- Connecting $p$ processors to $p$ memory banks with $\Theta(p\log p)$ switches with $\Theta(\log p)$ stages of $\Theta(p)$ switches each.
	- *Blocking* network, where even if the processors address distinct memory banks (permutation routing) can still have contention for switching elements.
	- Many specific versions, such as: Omega, Butterfly, Benes, etc.
