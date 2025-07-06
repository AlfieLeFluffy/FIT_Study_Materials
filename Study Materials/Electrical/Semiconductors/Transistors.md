Transistors are an electrical part that come either in the NPN or PNP variants and can be used to activate a circuit through an electric current. In other words they work like a switch but instead of mechanical power to close the connection they use an electrical current to do so. To do this they use the same principals of a PN junction as [[Diodes]] do, but in a new interesting way.

## Pins and Base Information
Both NPN and PNP transistors share connection names and some features. Both use the names Collector, Emitor and Base for the pins. These pins are each connected to a one of the semiconductor materials with Emitor being the most doped, Collector dope a bit less then that and Base doped the least. The base is also the thinnest layer.
Both version use to two NP junctions, but as alluded by their names in reverse order.
## NPN Transistor
An NPN transistor uses two outer layers of N-type and one middle P-type materials sandwiched in a series to essentially create two diode facing away from each other. 
![[NPN_Transistor]]
With NPN transistors the positive pole is connected to the Collector, the negative to the Emitor and to activate it a positive voltage of at least around 0.7V needs to be brought to the Base.
Within the conventional flow if a current of 0.20mA goes through the Collector and a current of 0.05mA goes through the Base then through the Emitor goes their combined total of 0.25mA. 
Within the electron flow the entire current goes through the emitor and then gets divided between the base and the collector. 
## PNP Transistor
An PNP transistor uses two outer layers of P-type and one middle N-type materials sandwiched in a series to essentially create two diode facing each other. 
![[PNP_Transistor]]
With PNP transistors the positive pole is connected to the Emitor, the negative to the Collector and to activate the transistor the base must be connected to the ground with voltage at least -0.7V lower then is on the emitor.
Within the conventional flow if a current of 0.25mA goes through the Emitor and the transistor is active then the current gets divided between the Base and the Collector, with the base taking 0.05mA and the Collector taking the rest, 0.20mA.

## Important Notes
- When adding a current to the base do not forget to lower it voltage through a resistor, otherwise the current will be too high and it will burn through the transistor junctions.
- The amount of current that goes through the transistor can be adjusted by increasing the current of the base.