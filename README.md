### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**
1.Declare a Verilog module named EXP11 with input ports clk, rst, sin, and an output port q.

2.Declare input ports: clk for the clock signal, rst for the reset signal, and sin for the input signal. Also, declare the output port q as a 4-bit vector representing the state of flip-flops.

3.Declare an internal register q as a 4-bit vector to store the state of the flip-flops.

4.Create an always block that triggers on the positive edge of both the clock (clk) and the reset signal (rst), containing the following steps:

5.If the reset signal is asserted (rst), assign q to 4'b0000 to reset all flip-flops to 0.

6.If the reset signal is not asserted, assign the value of sin to the first flip-flop (q[0]) and shift the values of q to the right.
/* write all the steps invloved */

**PROGRAM**
```
module expp11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @  (posedge clk)
begin
     if(!rstn)
	     out<=0;
	  else
	     out<=out+1;
end
endmodule
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:NENTHRANJI.S RegisterNumber:212224040216
*/

**RTL LOGIC UP COUNTER**
![expp11](https://github.com/user-attachments/assets/4d6d03d9-75d5-4c7f-bc29-3db776b48377)

**TIMING DIAGRAM FOR IP COUNTER**
![Screenshot (76)](https://github.com/user-attachments/assets/dea0759f-8b71-4054-a34b-0048a6ffc66a)

**TRUTH TABLE**
![WhatsApp Image 2025-05-14 at 14 18 20_a56dbc74](https://github.com/user-attachments/assets/bd71939e-736b-4464-bc93-fdbdfb19bee9)

**RESULTS**
Thus the 4 bit synchronous up counter and validate functionality has implemented
