Binary counters are combination circuits that add two binary numbers together.

## Half Adder
Realizes the addition of two one bit binary numbers (**A** and **B**) and outputs their sum (**S**) and carry (**C**). Half adder cannot take a carry input from a lower order. ![[Half_Adder]]
## Full Adder
Realizes the addition of three one bit binary numbers (**A**, **B** and **Cin**) and outputs their sum (**S**) and carry (**Cout**). Full adder can take a carry from a lower order and outputs its own carry. Technically the full adder is created by combining two half adders with an OR gate for both carries. ![[Full_Adder]]
## Ripple Carry Adder
Is created by connecting several full adders in a series so they can propagate their carry over to the next full adder. It is a pseudo-paraler adder, where the carry sequentially carries over through out the adder, which quite a slow process and only gets worse with the number of inputs.
Every carry bit has a delay of 3 logic gates and the sum has delay of 2 logic gates. From this we can say that the entire delay of this circuit is **S_i = 3\*(i-1) + 2 = 3\*i -1**. ![[Ripple_Carry_Adder]]
## Carry Select Adder
An expanded and quicker version of the Ripple Carry Adder that calculates possible carries in advance and then as the first Ripple Carry Adders finish work then the propagation of carry is not done through the adders but through multiplexors, choosing which future was correct depending on the outcome of the previous carry output. This way all of the additions take at max **S = 4 * 3 - 1 = 11** and then delays of the all the multiplexors on the way with each multiplexor taking 3 logic gate. ![[Carry_Select_Adder]]
## Carry Lookahead Adder
It is quicker then the Ripple Carry Adder and can be quicker then Carry Selection Adder. It functions in paralel and technically two binary numbers of any size can be added together with only a 4 logic gate delay with the carry calculations taking only 3.
In reality the size of the numbers is limited by the size of multi input logic gates with the equivalent delay to gates that have only inputs. It is impractical to calculate huge numbers in one go with this or any other Adder and so these calculations are usually segmented.
### Princip
The princip lies in the fact that from the table of inputs for the CLA one can deduce that the carry bit will be **C<sub>i+1</sub>= A<sub>i</sub> and B<sub>i</sub> or (A<sub>i</sub> or B<sub>i</sub>) and C<sub>i</sub>= G<sub>i</sub> or P<sub>i</sub> and C<sub>i</sub>**. The **G** value is Generate and the P value is Propagate.
For example if we were to calculate carries for number 1 to 4, we could say that:
- C<sub>1</sub> = G<sub>0</sub> + P<sub>0</sub> * C<sub>0</sub>
- C<sub>2</sub> = G<sub>1</sub> + P<sub>1</sub> * C<sub>1</sub>
- C<sub>3</sub> = G<sub>2</sub> + P<sub>2</sub> * C<sub>2</sub>
- C<sub>4</sub> = G<sub>3</sub> + P<sub>3</sub> * C<sub>3</sub>
Now if we substitute all of the carries (C<sub>i</sub>) with the one from lower order and propagated this technique up we would get:
- C<sub>1</sub> = G<sub>0</sub> + P<sub>0</sub> * C<sub>0</sub>
- C<sub>2</sub> = G<sub>1</sub> + P<sub>1</sub> * G<sub>0</sub> + P<sub>1</sub> * P<sub>0</sub> * C<sub>0</sub>
- C<sub>3</sub> = G<sub>2</sub> + P<sub>2</sub> * G<sub>1</sub> + P<sub>1</sub> * G<sub>0</sub> + P<sub>2</sub> * P<sub>1</sub> * P<sub>0</sub> * C<sub>0</sub>
- C<sub>4</sub> = G<sub>3</sub> + P<sub>3</sub> * G<sub>2</sub> + P<sub>2</sub> * G<sub>1</sub> + P<sub>1</sub> * P<sub>3</sub> * G<sub>0</sub> + P<sub>2</sub> * P<sub>1</sub> * P<sub>0</sub> * C<sub>0</sub>
To determine if a pair of number will generate a carry (G<sub>i</sub>) we can use:
- G<sub>i</sub> = A<sub>i</sub> * B<sub>i</sub>
To determine whether a bit will propagate a carry, we can use either:
- P<sub>i</sub> = A<sub>i</sub> ⊕ B<sub>i</sub>
- P<sub>i</sub> = A<sub>i</sub> + B<sub>i</sub>
From this we can assume that to calculate C<sub>i</sub> we need three logic gates (delays):
1. A xor B
2. P and C
3. or of all inputs
To calculate the sum of given order S<sub>i</sub> we can use:
- ( ( A<sub>i</sub> xor B<sub>i</sub> ) xor C<sub>i</sub> )
This means that the the final calculation is going to be one logic gate longer, so in total delay of 4 logic gates.
![[Carry_Lookahead_Adder]]
## Multibit adders with the use of 4-bit CLA
The 4-bit (and other) Carry Lookahead adders can be chained together using the Carry Lookahead outputs PG and GG.
- PG = P<sub>0</sub> + P<sub>1</sub> + P<sub>2</sub> + P<sub>3</sub>
- GG = G<sub>3</sub> + G<sub>2</sub> * P<sub>3</sub> + G<sub>1</sub> * P<sub>3</sub> * P<sub>2</sub> + G<sub>0</sub> * P<sub>3</sub> * P<sub>2</sub> * P<sub>1</sub>
The delay to calculated the final carry will be **C<sub>16</sub> = 4 * 3** and the time to calculate the final sum will be **S<sub>15</sub> = 3 * 3 + 4**.
Four of these 16-bit CLAs can then be chained together to create a 64-bit CLA and so on.