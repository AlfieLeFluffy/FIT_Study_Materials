An integrated circuit that implements a fully compatible computer ([[ALU]], [[Memory]], [[Network Interface]], etc.) that are possible to program and configure through some programming language such as C. MCUs also commonly unlike normal processors implement expanded functionality for interactions with outside values such as [[Convertor]]s, [[General Purpose Input Output (GPIO)]], [[Counter]]s, Timers, etc. They can be most commonly found in [[Embedded System]]s.
## Architectures
Microcontrollers usually implement one of two basic computer architectures:
![[Von Neuman Architecture]]

![[Harvard Architecture]]
## Instruction Sets
Microcontrollers just as general purpose computers can use one of two [[Instruction]] set architectures:
![[Complete Instruction Set Computing (CISC)]]

![[Reduced Instruction Set Computing (RISC)]]
## Structure
Most of the same components found in general purpose computers can be found in MCUs, but usually in a much smaller scale:
- **Processor**
- **Operating (main) memory** - [[RAM]]
- **Program memory** - [[Memory#Types|EEPROM, PROM, ROM, FLASH, ect.]]
- **Oscillator** - generates [[CLK]] signal
- [[General Purpose Input Output (GPIO)]]
## Peripheries
Most MCUs also provide some common peripheries:
- **Timer** - for example [[RTC]]
- **Clock** - source of clock signals usually done through a **crystal**
- [[Counter]]
- [[Convertor]]
- **Watchdog** - a module that keeps watch and prevents the MCU from deadlocking or getting stuck in case of an error. If the module does not receive a periodic notification it restarts the MCU.
- [[Field Programmable Gate Array (FPGA)]]
- [[Interrupt Controller]]
- **Sensors**
## Communications
For communication MCUs use one or more interfaces which are either [[Serial Interface|Serial]] or [[Parallel Interface|Parallel]]. Amongst the most common once are [[Universal Asynchronous Reciever-Transmiter (UART)]], [[Serial Peripheral Interface (SPI)]], [[Inter-Integrated Circuit (I2C)]], etc.