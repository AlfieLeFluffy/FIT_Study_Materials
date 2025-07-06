Communication with peripheries is controlled through a **Peripheral Devices Controller (PDC)** or just device controller.
## Functions
The controller which oversees:
- Communication with the [[CPU]]
- Generation of [[Interrupt|Interuptions]]
- Controlling and synchronization of peripheral operations
- Realization of cache
- Detection and reporting of faults
The controller [[Register]]s, through which the processor can communicate with the devices. These registers consist of **Data, Control and State** registers. 
## Device Mapping
Logically a device can be connected through two options:
- **Mapped IO** - The registers for controlling a device are mapped to the operation (main) [[Memory]] and the both the device and the system share an address space. The processor can then work with the device as if it was just part of the memory.
- **Isolated IO** - The main memory and the device do not share an address space and both have their own space. Operations with this device are done through special instruction such as IN, OUT or READ, WRITE.
## Physical Connection
There are also two ways of connecting the device to the computer:
- **Point-To-Point** - Between any devices in such a connection must run dedicated conductors that are exclusively used for their communication.
	- **Pros** - Shorter conductors, greater speeds, parallel communication with multiple devices.
	- **Cons** - Greater amount of conductors, more expensive, bigger complexity.
- [[Bus]] - More devices can be connected at one time through a smaller amount of conductors. Examples of such interfaces are [[Universal Serial Bus (USB)]], [[Peripheral Component Interconnect (PCI)]] , PCI-Express, [[Inter-Integrated Circuit (I2C)]].
	- **Pros** - Lower amount of conductors, cheaper, scalable, one input/output.
	- **Cons** - Lower speeds, slower transfer speeds, only one pair can communicate at a time, more complex communication.