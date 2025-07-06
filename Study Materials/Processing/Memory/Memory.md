**Memory** stores data and allows to (re)write and or read it later.

## Types
**By hierarchy**, which exists to get the best value to power ration. The closer to the processing unit the smaller nad more expensive the memory gets, but quicker it is. There are three main tiers in this hierarchy:
- **Primary** (Internal) memory is further split into:
	- **Inside processor** which consists of registers, cache, ([[Cache (RVP)]], usually several layers)
	- **Outside processor** which consists of [[RAM]]
- **Secondary** (Main) consists of [[HDD]]s and [[SSD]]s.
- **Tertiary** (External) consists of [[CD]]s, [[DVD]]s, [[Flash Disk]]s
**By volatility** into two groups:
- **Volatile** memory requires constant electrical upkeep or the data gets irreversibly wiped away.
- **Non-volatile** memory does not require constant electrical upkeep and so can be kept depowered and serves as long term storage option.
**By physical princip**, each with their upsides and downsides:
- [[Semiconductor]] memory consists of [[Flip-Flop]]s and [[SSD]]s
- Magnetic memory consists of [[HDD]]s, dissects and magnetic tapes.
- Optical memory consists of [[DVD]]s, [[CD]]s, Blue Rays.
- Magnetooptical
- Molecular
**By data retention:**
- **Static** memory stores data for any length of time (as long as it is connected to source of electricity). It is a quick, expensive memory with low capacity and is usually created with a large area of chips ([[Flip-Flop]]s).
- **Dynamic** memory stores the data only for a period of time before it needs to be refreshed. This means that every once in a while all of the data (in one go or partially) needs to be refreshed (re-powered or copied over itself) in order to keep the data alive. This is slower then static memory, but also it is cheaper and requires a smaller area on the chip. Usually used for DRAM memory.
**By data access:**
- **Random** access ([[RAM]], Random Access Memory) does not restrict what part of the memory can be accessed and so any part can be worked with at any time.
- **Serial** access ([[SAM]], Serial Access Memory) restricts access to the data by its location. This is for example serial access on tapes. 
- **Mixed** access both types of access due to physical or logical restrictions. This can for example be found in [[HDD]]s that combine random access to sectors with the nature of how sectors are worked with in series.
**By accessibility/changability:**
- **ROM** (Read Only Memory)
- **PROM** (Programable ROM)
- **EPROM** (Erasable PROM)
- **EEPROM** (Electronically EROM)
- **RWM** (Read Write Memory)

## Memory Properties
- **Capacity**
- **Access Time**
- **Transfer Speed**
- **Error Rate**
- **Fault Rate**
## Locality Principal
The processes (applications, programs) only usually work with a small part of the memory space (code, data, etc...).
- **Time Locality** if the processor uses some element stored in memory it is usually beneficial to store is as close to the processor as possible.
- **Space Locality** if the processor uses some element stored in memory that elements surrounding this one are more likely to be used next so it is beneficial to stores them as close to the processor as well to minimize load times.
