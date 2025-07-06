Counter (čítače) are a special type of state machines (speciální automaty) that react to the input impulses (like the rising or falling edge) with moving from one state to another state (incrementing or decrementing).
## Types
Divided by synchronisty:
- **Asynchronous** counter do not contain enable (control, clock) inputs and the counting is only driven by the input.
- **Synchronous** counter are controlled by an enable (control, clock) signal and can only count (change state) while enabled by that signal.
Can have control inputs that enable:
- **UP/DOWN** specify the direction of counting (incrementing/decrementing).
- **[[CE]]** only remembers while in log. 0, counts in log. 1.
- **P Enable** counts when in log. 1 and does not influence **RCO**.
- **T Enable** counts when in log. 1.
Can have output that indicate overflow (underflow) of the counter:
- **[[RCO]]** or **TC**
To increase the time to count / division ration / counter overflow are implemented with cascading (sequential) connection of multiple counters. Counters are connected by input **[[CE]]** onto output **[[RCO]] (TC)** of the previous counter.
	For example three counter MOD10 connected in a sequence overflow only once in a 10 * 10 * 10 = 1000 impulses/cycles.

### T Flip-Flop Counter
They can be for example 4-bit counters that can count from 0 to 15 and then have a ripple carry out when overflowing with the current state of the counter on the T Flip-Flop outputs of Q<sub>0</sub> to Q<sub>3</sub>.
![[T_Flip-Flop_Counter]]
### Gray Code Counter
The counter uses [[Gray Code]]. This way the counter only has to move one bit per counter operation instead of multiple on order changes and such.
![[Gray Code]]
### Up/Down Counter

### One-Hot (Straight) Counter
Uses D flip-flops setup in a cascade (sequence) where only one of the D flip-flops in in log. 1.
![[One-Hot_Counter]]

### Johnson Code Counter
Also uses the D flip-flop, but instead of only one being active, they use the [[Johnson Code]], which means they slowly fill up and empty over time with the negated output of the last as the input to the first.
![[Johnson Code]]
![[Johnson_Code_Counter]]
