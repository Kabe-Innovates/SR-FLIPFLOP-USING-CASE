# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**
1. Define Inputs/Outputs: Inputs: S (Set), R (Reset), c1k (clock); Outputs: Q, Qbar.
2. Initialization: Set Q = 0 and Qbar = 1 at the start of the simulation.
3. SR Flip-Flop Logic: On posedge c1k, compute Q = S | (~R & Q).
4. Complementary Output: Update Qbar = R | (~S & Qbar) to maintain SR Flip-Flop behavior.
5. Testbench: Test with combinations of S, R, and c1k to ensure proper Set-Reset functionality.

**PROGRAM**
```

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
Developed by: KABELAN G K 
RegisterNumber: 24900985
*/
```
```
module exp6(S,R,c1k,Q,Qbar);
input S,R,c1k;
output reg Q;
output reg Qbar;
initial Q=0;
initial Qbar=1;
always @(posedge c1k)
begin
Q=S|((~R)&Q);
Qbar=R|((~S)&(Qbar));
end
endmodule

```

**RTL LOGIC FOR FLIPFLOPS**
![image](https://github.com/user-attachments/assets/7f2123ea-f1ee-40fa-acba-5daf01313ec8)


**TIMING DIGRAMS FOR FLIP FLOPS**
![image](https://github.com/user-attachments/assets/3ada51b7-62e4-4a46-b149-239451bac46f)


**RESULTS**

Thus the SR flipflop is implemented and verified.
