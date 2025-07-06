Commonly a **embedded system/s** can be defined as a combination of hardware and software with the purpose of controlling and external process, device or system. 
They are single purpose computers integrated into a device they control. In contrast to general purpose computers, embedded systems are specialized and have a predefined task (routine) that they control. They can be found in things like vending machines, washing machines, automobiles, lifts, etc...
## Common Goals
Embedded systems should be:
- **Autonomous** - Function without human interference.
- **Reactive** - Should react to inputs in real time.
- **Critical Functionality** - Should function in a safe manner even in deviations from normal behaviour.
## Common Properties
Some properties that embedded systems share are:
- They usually cary out only one application, one routine, usually for their entire lifetime.
- They commonly work with physical quantities.
- They should be reliable, safe, secured and effective.
- Their main interactions does not have to be with a human.
- An ideal outcome is for a human to not even realize or think about the fact they are interacting with a computer.
## Shared Base
Even as embedded systems are specialized in their function it is not feasible to design a new specific circuit for each application. Such an approach would be costly both from manufacturing and design point of view and possible repairs would be complicated by specialized parts and complex designs. To solved this issue most embedded system use a common base circuit that is designed to allow modular expansion, custom scripting, shared interfaces, which can be manufactured cheaply on mass. These circuits are called [[Microcontroller (MCU)]].
