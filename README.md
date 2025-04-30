# REG NO: 212223230245
# DEVELOPED BY: VINODHINI K
# T-FLIPFLOP-POSEDGE

**AIM:**

To implement  T flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**T Flip-Flop**

T flip-flop is the simplified version of JK flip-flop. It is obtained by connecting the same input ‘T’ to both inputs of JK flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of T flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/458a68fe-2d08-4a9d-ac4f-7ae0480ce0bd)

 
This circuit has single input T and two outputs Qtt & Qtt’. The operation of T flip-flop is same as that of JK flip-flop. Here, we considered the inputs of JK flip-flop as J = T and K = T in order to utilize the modified JK flip-flop for 2 combinations of inputs. So, we eliminated the other two combinations of J & K, for which those two values are complement to each other in T flip-flop. The following table shows the state table of T flip-flop.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, T flip-flop can be used for one of these two functions such as Hold, & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of T flip-flop. Inputs Present State Next State

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/cdd7fb32-539f-4b66-bb8d-f305a153c886)

 
From the above characteristic table, we can directly write the next state equation as Q(t+1)=T′Q(t)+TQ(t)′ ⇒Q(t+1)=T⊕Q(t)

**Procedure**

1.Understand the T flip-flop truth table: T=0 → No change, T=1 → Toggle.

2.Write Verilog code using always block triggered on clock edge.

3.Create a testbench to apply clock and T input combinations.

4.Simulate the design using a Verilog simulator (e.g., ModelSim or iverilog).

5.Compare output Q with expected values from the truth table to validate.

**PROGRAM**

```
module exp9(t, clk, rst, q);
  input t, clk, rst;
  output reg q;

  always @(posedge clk or posedge rst) 
begin
    if (rst)
      q <= 0; // Reset the flip-flop
    else if (t==0)
      q <= q; 
     else
        q<=~q;
  end
endmodule
```
**RTL LOGIC FOR FLIPFLOPS**
![Screenshot (57)](https://github.com/user-attachments/assets/374e4e8d-02aa-453e-b258-eecad926b7c7)


**TIMING DIGRAMS FOR FLIP FLOPS**
![Screenshot 2025-04-29 185244](https://github.com/user-attachments/assets/a6d8537f-4004-4c19-9a6d-3515d12fc3f0)


**RESULTS**
Thus the implemented T-flipflop are successfully verified.
