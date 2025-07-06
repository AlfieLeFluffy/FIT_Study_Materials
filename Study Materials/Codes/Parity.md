Parity is a simple code principle for detection of errors (faults) in code. There are two types of parity:
- **Odd**
- **Even**
These types refer to if the final code should have either an odd or even amount of logic ones. This can be demonstrated as:
```
7 bit code of: 10 01 11 0
for odd parity we add a 1 to the end: 10 01 11 01
for even parity we add a 0 to the end: 10 01 10 00
```
In the example above we can quickly assess if a code was altered by looking at the parity bit (in this case the last one) and comparing that against the rest of the code and the parity type we set. If the parity bit does not match then there was an error somewhere and this data has been altered.