MOSFET also known as *Metal Oxide Semiconductor Field Effect Transistor* is a [[Semiconductor]] electrical component that works on the same way as a transistor, but with a different principal. Instead of using both types of silicon it uses only on to conduct current, with the other one acting as a isolation to close the transistor.

## Pins and Base Information
MOSFETs have three pins labelled:
- **Source** is connected to a one electrode (node).
- **Drain** is connected to a one electrode (node) and the substrate (body).
- **Gate** is the control pin (like Base in [[Transistors]]), but instead of combining or dividing the current, this pin only holds the current like a capacitor.

The electrodes are highly doped while the substrate is lightly doped.
## Types
There are four base types of MOSFETs that can be distinguished by two properties.

First property is how it behaves deactivated and activated:
- **Enhancement** type is closed when deactivated and open when activated. This essentially works as a normal transistor.
- **Depletion** type is open when deactivated and closed when activated, essentially the opposite of both enhancement type and normal transistors.

Second property is which silicon type it uses to conduct electricity (the channel in these names refers to the channel that is created when the MOSFET is open):
- **N-channel** uses N-type silicon for nodes and P-type as substrate.
- **P-channel** uses P-type silicon for nodes and N-type as substrate. 

![[MOSFET_Diagrams]]

## Princip
### N-Channel example
For example of the principal, an N-channel enhancement MOSFET has are two N-type electrodes (nodes) imbedded into a substrate (body) made from P-type. There is not direct connection between the N-type electrodes. ![[N-channel_MOSFET_Closed]]
If a positive pole would be brought to the Source pin and a negative pole would be brought to the Drain pin, nothing would happen as there is no way for the current to move through the P-type substrate.
To open the MOSFET a positive voltage would have to be brought to the Gate pin, which would due to the dielectric layer not conduct through the P-type substrate, but like a capacitor would create an electromagnetic field that would repel the free electrons in the substrate, creating an N-type channel through which electricity could conduct from the Source to the Drain (if looking at it in electron flow the electrons could flow from the Drain to the Source).![[N-channel_MOSFET_Open]]
The same idea is applied for the Depletion type of N-channel MOSFETs, but instead of creating a channel (bridge), one already exists, is created within the MOSFET, and bringing negative charge on the gate would close it as it would attract the free electrons from the P-type substrate and thus creating changing the N-type channel to a P-type substrate.
### N-Channel example
This principal is also the same principal for the P-channel MOSFETS, but in reverse. ![[P-channel_MOSFET_Closed]]![[P-channel_MOSFET_Open]]
## Performance
Performance-wise the MOSFET is much quicker and can carry much greater currents then [[Transistors]]. This makes it perfect for applications such as [[Pulse Width Modulation]] (PWM). One downside of MOSFETS, especially if used in high throughput is heat, requiring heatsinks in order to not overheat and melt.
## Important Notes
- When a powering the Gate pin it is highly recommended to do so through a resistor as the sudden spike in current might cause a controlling circuit, like a microcontroller, to get damaged. ![[MOSFET_Gate_Protection]]
- Unlike in [[Transistors]], where the Base pin's current got combined into or divided from the Emitor pin, the gate pin essentially works as a capacitor so it is important to create a way for the charge to leave in order to return the MOSFET back into the its default state. This can be done adding a connection to ground through a high resistance resistor. That way a small amount of current will still flow to the ground, but this will allow the Gate pin to discharge  safely. It is also important to place the draining resistor before the protection resistor, otherwise it would only create a voltage divider. ![[MOSFET_Gate_Draining]]
