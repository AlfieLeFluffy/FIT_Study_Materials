SPI is a serial synchronous interface of type **Master-Slave** that is [[Full-Duplex]], but a cheaper option is to make it through a bus.
## Components
- **Master** - Only one master can exist on bus and is the source of the [[CLK]] signal, initiates and controls communication.
- **Slave** - To the bus can be connected multiple slaves devices. The master designates with which he wants to communicate.
## Conductors
- **MISO** (Master In, Slave Out)
- **MOSI** (Master Out, Slave In)
- **SPSCK** (SPI Serial Clock)
- **SS** (Slave Select)