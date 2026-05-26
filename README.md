# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**


Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

Step 1: Create New Project

Open Quartus II.

Click File → New Project Wizard.

Select a folder, give project name JK_FlipFlop, click Next.

Select device (or keep default) → Finish.

Step 2: Create Block Diagram

Click File → New → Block Diagram/Schematic File.

Save the file as jk_ff.bdf.

Step 3: Insert JK Flip-Flop

Double-click inside the diagram.

Select Primitives → Storage → Flipflop.

Choose JK Flip-Flop and click OK.

Place it on the schematic.

Step 4: Add Input & Output Pins

Insert Input pins and name them:
Insert Output pins and name them:
Step 5: Make Connections

Connect J, K, CLK to the JK flip-flop inputs.

Connect Q and Q̅ to output pins.

Save the schematic.

Step 6: Compile the Design

Click Processing → Start Compilation.

Ensure Compilation Successful message appears.

Step 7: Create Simulation File

Click File → New → University Program VWF.

Go to Edit → Insert Node or Bus.

Select J, K, CLK, Q, QBAR.

Set clock waveform for CLK.

Apply input values for J and K.

Step 8: Run Simulation

Click Simulation → Run Functional Simulation.

Observe the outputs Q and Q̅.

Verify output with truth table.

**PROGRAM**
```
module jkff(j,k,clk,q,qbar);
input j,k,clk;
output reg q,qbar;
initial 
begin
q=1'b0;
q=1'b1;
end 

always @(posedge clk)
begin 
q<=(j&~q)|(~k&q);
qbar<=~q;
end
endmodule
```

**RTL LOGIC FOR FLIPFLOPS**

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/969a12ce-3059-4372-bb0b-3d0e7054a790" />

**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1600" height="850" alt="image" src="https://github.com/user-attachments/assets/08325435-e0fa-4f1e-8a82-329dfaf31081" />


**RESULTS**
The JK Flip-Flop was successfully designed and simulated using Quartus II and its truth table is verified.
