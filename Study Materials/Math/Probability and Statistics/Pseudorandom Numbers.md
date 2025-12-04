---
tags:
  - IPT
aliases:
  - pseudorandom numbers
---
## Generation of Pseudorandom Numbers
### Types
- **Physical Source of Randomness** uses a sensor device (temperature, acceleration, position, lava lamps, ...) the number is generated through truly random variable. The issues with this approach can be speed as the system can be restricted in the way it collect information.
- **Algorithm Generator** generate pseudorandom (deterministic) number. These do not have the issue of throughput, but suffer from determinism and loops.
### Congruency Generator
Uses constants **a**, **b** that must be chosen carefully otherwise it will lead to poor quality numbers. The final number is also cut into a shape using **mod m**, where **m** is the desired length.
$$x_{n+1} = (ax + b) mod \ m$$
They generate:
- **Even Distribution**
- **A finite amount of elements in order** - they have a period by which they cycle.
#### Requirements
- **Distribution Evenness**
- Statically **independency of the generated ordered set**
- The **longest period**
- Speed
### Mersenne Twister

### Xorshift