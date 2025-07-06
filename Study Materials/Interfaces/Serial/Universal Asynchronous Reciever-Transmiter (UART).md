As the name implies this is a **asynchronous** [[Serial Interface]].
## Properties
- UART communication is usually [[Full-Duplex]], but can also be a [[Half-Duplex]] or just a [[Simplex]].
## Communication Description
- Synchronization is done through a **start bit**, that is sent at the beginning of each transferred frame. It is done through going from the quite level log. 1 to log. 0.
- After the **start bit** the transmiter sends **data bits** (usually 8 bits).
- After **data bits** the transmiter can also send a **parity bit** (low/high).
- The end of the transmission is signified by **two stop bits**, which are log. 1 values that *level out* the system back to the quite state. 
- The transmitted value is done from [[LSB]] to [[MSB]].