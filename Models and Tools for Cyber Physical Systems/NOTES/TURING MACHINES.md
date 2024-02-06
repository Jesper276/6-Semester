1. A Turing machine can both write on the tape and read from it.
2. The read-write head can move both to the left and to the right.
3. The tape is infinite.
4. The special states for rejecting and accepting take effect immediately.

## FORMAL DEFINITION OF A TURING MACHINE
- The heart of the definition of a Turing machine is the transition function δ because it tells us how the machine gets from one step to the next.
- For a Turing machine, δ takes the form: $Q×Γ → Q×Γ×{L, R}$
- That is, when the machine is in a certain state q and the head is over a tape square containing a symbol a, and if $δ(q, a) = (r, b,L)$ the machine writes the symbol b replacing the a
- The third component is either L or R and indicates whether the head moves to the left or right after writing
![[Pasted image 20240206110600.png]]
A Turing machine M computes as follows.
1. Initially, M receives its input $w = w1w2 . . . wn ∈ Σ^∗$ on the leftmost n squares of the tape, and the rest of the tape is blank (i.e., filled with blank symbols).
2. The head starts on the leftmost square of the tape
- Note that Σ does not contain the blank symbol, so the first blank appearing on the tape marks the end of the input.
3. Once M has started, the computation proceeds according to the rules described by the transition function. If M ever tries to move its head to the left off the left-hand end of the tape, the head stays in the same place for that move, even though the transition function indicates L
4. The computation continues until it enters either the accept or reject states, at which point it halts. If neither occurs, M goes on forever.
As a Turing machine computes, changes occur in the **current state**, **the current tape contents**, and **the current head location**. A setting of these three items is called a **configuration of the Turing machine**.
For a **state q** and **two strings u and v** over the tape **alphabet Γ**:
- we write $u q v$
- for the configuration where the current state is q
-  The current tape contents is uv
- And the current head location is the first symbol of v
### Example:
1011q701111
represents the configuration when the tape is 101101111
The current state is q7, and the head is currently on the second 0

### Accept, reject and loop
When we start a Turing machine on an input, three outcomes are possible. The machine may *accept, reject, or loop*.
- In an accepting configuration, the state of the configuration is $q_{accept}$.
- In a rejecting configuration, the state of the configuration is $q_{reject}$
- loop we mean that the machine simply does not halt. Looping may entail any simple or complex behavior that never leads to a halting state.

## EXAMPLES OF TURING MACHINES
![[Pasted image 20240206111739.png]]

Each iteration of stage 1 cuts the number of 0s in half. As the machine sweeps across the tape in stage 1, it keeps track of whether the number of 0s seen is even or odd. If that number is odd and greater than 1, the original number of 0s in the input could not have been a power of 2. Therefore, the machine rejects in this instance. However, if the number of 0s seen is 1, the original number must have been a power of 2. So in this case, the machine accepts. Now we give the formal description of $M2 = (Q, Σ, Γ, δ, q1, q_{accept}, q_{reject})$:

- Q = $\{q_1, q_2, q_3, q_4, q_5, q_{accept}, q_{reject}\}$, 
- $Σ = {0}$, and 
-  $Γ = {0,x,�}$. 
-  We describe δ with a state diagram (see Figure 3.8). 
-  The start, accept, and reject states are $q_1$, $q_{accept}$, and $q_{reject}$, respectively.
- ![[Pasted image 20240206112349.png]]
- In this state diagram, the label 0→�,R appears on the transition from q1 to q2. This label signifies that when in state q1 with the head reading 0, the machine goes to state q2, writes �, and moves the head to the right.
- In other words, δ(q1,0) = (q2,�,R)
- For clarity we use the shorthand 0→R in the transition from q3 to q4, to mean that the machine moves to the right when reading 0 in state q3 but doesn’t alter the tape, so δ(q3,0) = (q4,0,R).
- This machine begins by writing a blank symbol over the leftmost 0 on the tape so that it can find the left-hand end of the tape in stage 4. Whereas we would normally use a more suggestive symbol such as # for the left-hand end delimiter, we use a blank here to keep the tape alphabet, and hence the state diagram, small.
- ![[Pasted image 20240206112552.png]]
- 