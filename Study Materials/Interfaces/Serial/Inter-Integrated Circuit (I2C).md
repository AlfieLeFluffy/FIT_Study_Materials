I2C is a serial synchronous interface that uses the **Master-Slave** architecture. It only communicates through [[Half-Duplex]].
## Conductors
- **SDA** (Serial Data)
- **SCL** (Serial Clock)
## Communication Description
- Commonly only uses data frames of 1 byte. 
- Each frame is ended by **ACK** (acknowledgement) from a slave.
- To select which slave device the master wants to communicate with is designated in their first data frame that has a 7 bit address (so 128 devices).