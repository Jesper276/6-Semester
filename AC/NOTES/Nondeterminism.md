When the machine is in a given state and reads the next input symbol, we know what the next state will be-it is determined. We call this deterministic computation. In a nondeterministic machine, several choices may exist for the next state at any point.
nondeterministic finite automaton, abbreviated NFA
![[Pasted image 20240206105021.png]]
- Man skal ikke vise alle veje i en nondeterminism man skal bare vise den vej der er rigtig
## FORMAL DEFINITION OF A NONDETERMINISTIC FINITE AUTOMATON
A nondeterministic finite automaton is a 5-tuple $\left(Q, \Sigma, \delta, q_0, F\right)$, where
1. $Q$ is a finite set of states,
2. $\Sigma$ is a finite alphabet,
3. $\delta: Q \times \Sigma_{\varepsilon} \longrightarrow \mathcal{P}(Q)$ is the transition function,
4. $q_0 \in Q$ is the start state, and
5. $F \subseteq Q$ is the set of accept states.