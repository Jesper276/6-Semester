## FORMAL DEFINITION OF A FINITE AUTOMATON
A finite automaton is a 5-tuple $\left(Q, \Sigma, \delta, q_0, F\right)$, where
1. $Q$ is a finite set called the states,
2. $\Sigma$ is a finite set called the alphabet,
3. $\delta: Q \times \Sigma \longrightarrow Q$ is the transition function, ${ }^1$
4. $q_0 \in Q$ is the start state, and
5. $F \subseteq Q$ is the set of accept states. ${ }^2$

## THE REGULAR OPERATIONS
Let $A$ and $B$ be languages. We define the regular operations union, concatenation, and star as follows:
- Union: $A \cup B=\{x \mid x \in A$ or $x \in B\}$.
- Concatenation: $A \circ B=\{x y \mid x \in A$ and $y \in B\}$.
- Star: $A^*=\left\{x_1 x_2 \ldots x_k \mid k \geq 0\right.$ and each $\left.x_i \in A\right\}$.