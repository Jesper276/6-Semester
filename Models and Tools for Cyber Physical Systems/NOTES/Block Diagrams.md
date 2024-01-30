![[Pasted image 20240130165541.png]]
- **Instantiation:** 
	- The components Delay1 and Delay2 are both instances of the component Delay.
	- Such instances are obtained by renaming the input/output variables.
	- For example, the component Delay1 is exactly like the component Delay except its output variable is called temp instead of out.
- **Parallel Composition:**
	- The two components Delay1 and Delay2 run in parallel. 
	- The block diagram shows that the output of the component Delay1 is the same as the input of the component Delay2, and this achieves communication between the two components.
	- The communication is synchronous. In each round, the component Delay1 reads its input in, produces output temp, and updates its internal state to record the current value of in.
	- In the same round, the component Delay2 reads its input temp — as supplied by the component Delay1, produces its output out, and updates its internal state to record the current value of temp.
- **Output Hiding:**
	- For the component DoubleDelay, the relevant output variable is out, and the variable temp is only an auxiliary variable that is used in implementing DoubleDelay. 
	- The block diagram shows that the variable temp is local by having it in the same box and not exported to the outside world. 
	(Delay$[$ out $\mapsto$ temp $] || $Delay$ $[$ in $\mapsto$ temp $])$ $\backslash$ temp.
## parallel composition ||


## renaming $\mapsto$
- is not *implicit*
- The renaming of *input/output* variables needs to be defined *explicitly*
## hiding $\backslash$
- What variable should not be shown