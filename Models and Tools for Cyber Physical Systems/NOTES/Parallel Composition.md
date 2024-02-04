# parallel composition ||
- The parallel composition operation combines two components into a single component whose behavior captures the synchronous interaction between the two components running concurrently.
- the parallel composition operation is commutative
- The parallel composition is also associative
- If both the components C1 and C2 are finite-state, then so is the product C||C2
- If $C_1$ has $n_1$ states and $C_2$ has $n_2$ states, then $C_1||C_2$ has $N_1 ∗ n_2$ states
 
 ## **state-space explosion problem:**
<p style="text-align:center;">*If we were to compose n instances of the component Delay in a chain to construct a component that outputs, in each round, the value of the input n rounds earlier, then it will have 2n states. The fact that the number of states grows exponentially with the number of components poses a challenge to analysis tools in terms of scalability*</p>
## Compatibility in Variable Names
- First, there should be no name conflicts concerning state variables
- The set S1 should be disjoint from each of the sets I2, O2.
- a variable can be an input variable to both the components, and an output variable of one component can be an input variable to the other, but a variable cannot be an output variable of both the components
## Product Variables
-  Denoted C1||C2, to be another synchronous reactive component C.
- We will also refer to the composition C as the synchronous product of the components C1 and C2
- ### Output
- the set O of output variables of C is the union O1 ∪ O2
- Each input variable of a component is an input variable of the product, provided it is not an output variable of the other component
- ### Input
- That is, the set I of input variables of C is the set (I1 ∪ I2) \ O, denoting the difference of the two sets I1 ∪ I2 and O.
## Product States
- A state of the product C assigns values to variables in $S_1$ as well as variables in $S_2$
- ### initialization
- The initial states of C are obtained by choosing the values for variables in S1 according to the initialization $Init_1$ of the component C1
- If the two initializations $Init_1$ and $Init_2$ are given as sequences of assignment statements
- then the initialization $Init$ for the product can be defined to be $Init_1;Init_2$ or, equivalently, $Init_2;Init_1$ since there can be no write-conflicts in the two blocks of initial assignments
## Reaction Description of the Product
- Combinational component that sets its output to the negation of its input. This form of cyclic composition is called feedback composition
- “If a task A belonging to one component reads a variable y, which is an output variable of the other component, then add a precedence edge from the unique task that writes y to the task A.”
## Acyclicity of Await Dependencies
- COMPONENT COMPATIBILITY
	- The components $C_1$ with input variables $I_1$, output variables $O_1$, and input/output await-dependency relation $\succ_1 \subseteq O_1 \times I_1$, and $C_2$ with input variables $I_2$, output variables $O_2$, and input/output await-dependency relation $\succ_2 \subseteq O_2 \times I_2$, are said to be compatible if (1) the sets $O_1$ and $O_2$ are disjoint, and (2) the relation $\left(\succ_1 \cup \succ_2\right)$ is acyclic.
- Component Composition
Let $C_1=\left(I_1, O_1, S_1\right.$, Init $_1$, React $\left._1\right)$ and $C_2=\left(I_2, O_2, S_2\right.$, Init $_2$, React $\left._2\right)$ be compatible synchronous reactive components. Suppose the reaction description React $_1$ is given using local variables $L_1$ by a task graph with the set $\mathcal{A}_1$ of tasks and the precedence relation $\prec_1$, and the reaction description React $_2$ is given using local variables $L_2$ by a task graph with the set $\mathcal{A}_2$ of tasks and the precedence relation $\prec_2$. Then the parallel composition $C_1 \| C_2$ is a synchronous reactive component $C$ such that:
- the set $S$ of state variables is $S_1 \cup S_2$;
- the set $O$ of output variables is $O_1 \cup O_2$;
- the set $I$ of input variables is $\left(I_1 \cup I_2\right) \backslash O$;
- the initialization for a state variable $x$ is given by Init $_1$ for $x \in S_1$ and by Init $_2$ for $x \in S_2$; and
- the reaction description of $C$ uses the local variables $L_1 \cup L_2$ and is given by the task graph such that (1) the set of tasks is $\mathcal{A}_1 \cup \mathcal{A}_2$, and (2) the precedence relation is the union of $\prec_1$ and $\prec_2$ and task pairs $\left(A_1, A_2\right)$, such that $A_1$ and $A_2$ are tasks of different components with some variable occurring in both the write-set of $A_1$ and the read-set of $A_2$.