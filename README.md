<img width="613" height="374" alt="Screenshot 2025-12-14 182439" src="https://github.com/user-attachments/assets/fd0ac80b-ba3b-4d07-9aad-d1ad7ea4903e" />AIM:

To implement T flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

T Flip-Flop

T flip-f
op is the simplified version of JK flip-flop. It is obtained by connecting the same input ‘T’ to both inputs of JK flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of T flip-flop is shown in the following figure.

image

<img width="613" height="374" alt="Screenshot 2025-12-14 182439" src="https://github.com/user-attachments/assets/3140a9ba-650c-4d92-8d20-d15c2c9e5ff8" />


This circuit has single input T and two outputs Qtt & Qtt’. The operation of T flip-flop is same as that of JK flip-flop. Here, we considered the inputs of JK flip-flop as J = T and K = T in order to utilize the modified JK flip-flop for 2 combinations of inputs. So, we eliminated the other two combinations of J & K, for which those two values are complement to each other in T flip-flop. The following table shows the state table of T flip-flop.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, T flip-flop can be used for one of these two functions such as Hold, & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of T flip-flop. Inputs Present State Next State


<img width="450" height="364" alt="Screenshot 2025-12-14 182448" src="https://github.com/user-attachments/assets/07edbbdb-af70-4abd-bcda-4d24f86babe8" />


From the above characteristic table, we can directly write the next state equation as Q(t+1)=T′Q(t)+TQ(t)′ ⇒Q(t+1)=T⊕Q(t)



PROGRAM
module T (
    input  wire clk, rst, T,
    output reg Q 	  
);

  initial begin
     Q<=1'b0;
	 end
  
  
	 always @(posedge clk or posedge rst) begin
	
        if (rst)
            Q <= 1'b0;       // Reset
        else if (T)
            Q <= ~Q;         // Toggle if T=1
        else
            Q <= Q;          // Hold if T=0
    end
endmodule


Developed by:B.SASIREKHA

RegisterNumber: 25015734

RTL LOGIC FOR FLIPFLOPS

TIMING DIGRAMS FOR FLIP FLOPS

RESULTS
