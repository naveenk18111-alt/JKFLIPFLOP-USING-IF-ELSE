# JKFLIPFLOP-USING-IF-ELSE
# Developed By: NAVEENKUMAR V
# Ref.No: 25016071
## AIM:
To implement  JK flipflop using verilog and validating their functionality using their functional tables

## SOFTWARE REQUIRED:
Quartus prime

## THEORY:

### JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

## Procedure:
1.  Start a new project in Quartus Prime and create a Verilog file for implementing the JK flip-flop.
2.  Write the Verilog code for the JK flip-flop using behavioral modeling with if–else or logical expressions.
3.  Compile the project to check for syntax errors and generate the RTL schematic for verification.
4.  Create a testbench and run the RTL simulation to observe the waveform of J, K, CLK, Q, and Q̅.
5.  Compare the simulated output with the JK flip-flop truth table to verify correct flip-flop functionality.

## PROGRAM:
```
module jkflipflop(
input clk,
input j,
input k,
output reg q,
output reg qbar
);

always @(posedge clk) begin
if (j == 0 && k == 0) begin
    q <= q;
    qbar <= qbar;
end 
else if (j == 0 && k == 1) begin
    q <= 0;
    qbar <= 1;
end 
else if (j == 1 && k == 0) begin
    q <= 1;
    qbar <= 0;
end 
else if (j == 1 && k == 1) begin
    q <= ~q;
    qbar <= ~qbar;
end
end

endmodule
```

## RTL LOGIC FOR FLIPFLOPS:
<img width="1920" height="1080" alt="DE  jkflipflop-5 1" src="https://github.com/user-attachments/assets/7f26cce8-7376-4fc6-b87e-7942a0d0810b" />

## TIMING DIGRAMS FOR FLIP FLOPS:
<img width="1920" height="1080" alt="DE jkflipflop-5 2" src="https://github.com/user-attachments/assets/4dbc7569-1132-4591-90b2-a7e17456f90b" />

## RESULTS:
Thus the JK flipflop is implemented and verified.
