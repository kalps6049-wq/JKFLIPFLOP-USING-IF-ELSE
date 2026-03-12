# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime


**JK Flip-Flop:**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure:**
Open Quartus Prime and create a new Verilog project.

Write the Verilog code for the JK flip-flop.

Compile the project to check for errors.

Generate the RTL schematic to verify the correct logic design.

Create a testbench to simulate the functionality of the JK flip-flop.

Apply various input combinations for J and K.

Observe the next state Q(t+1) based on the characteristic table.

Generate the timing diagram to verify the behavior of the flip-flop with respect to the clock signal.

Validate the simulation results against the functional table.

**PROGRAM:**
```
module exp3 (q, qb,j,k,clock,reset);
    input j,k,clock,reset;
    output reg q, qb;
	 
always @ (posedge (clock))

    begin 
        if (!reset)
            begin
               q <= q;
               qb <=qb;
            end   
        
else
 //Write logic for JK flipflop using if else statement for four conditions

begin
               if (j == 0 && k == 0)
                    begin
                    q <= q;
                    qb <= qb;
                    end 
		else if (j != k)
                    begin
                    q <= j;
                    qb <= k;
                    end
               else if (j == 1 && k == 1) 
                    begin 
                    q <= ~q; 
                    qb <= ~qb; 
                    end 
            end
end  
endmodule
```

**RTL LOGIC FOR FLIPFLOPS:**
<img width="1920" height="1080" alt="Screenshot (83)" src="https://github.com/user-attachments/assets/a4c50f30-a702-4540-932e-29d9b1cad001" />



**TIMING DIGRAMS FOR FLIP FLOPS:**
<img width="1920" height="1080" alt="Screenshot (84)" src="https://github.com/user-attachments/assets/484a9ef9-8b4a-4e25-a5c3-68deb4c1ae25" />


**RESULTS:**
The JK flip-flop was successfully implemented in Verilog, and its functionality was validated using the truth table and timing diagrams. The output correctly responds to all input combinations, including toggling when J = 1 and K = 1.
