Unlike with [[Combination Circuit]]s, the output of the sequence logic circuits (Sekvenční obvody - SO) is not only dependent on the current input, but also on the previous inputs that the circuit stores. They are comprised of combination part and a memory part. The memory in sequence circuits stores the internal (current) state.

### Types
There are two main types of sequence circuits and those are asynchronous and synchronous.
- **Asynchronous** SO make changes as soon as the inputs change, e.i. they react immediately.
- **Synchronous** SO are controlled by a clock signal. They react to inputs only when their clock condition is met, which is in some periodical intervals.
	- **Level** (úrovňové) SO watch inputs for the entire time for the clock signal and react to them continuously.
	- **Edge** (hranové) SO only react to inputs on the edge of the clock signal (up or down edge).
