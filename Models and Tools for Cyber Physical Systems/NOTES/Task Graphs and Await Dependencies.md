$$ A : x_1, x_2,...x_m \mapsto  y_1, y_2,...y_n $$
indicates that the task A has the read-set $R = {x_1, x_2,...x_m}$ and the write-set $W = {y_1, y_2,...y_n}$. The update description of a task describes its computation as a sequence of assignment and conditional statements or, alternatively, using the extended-state machine notation

- We write A1 ≺ A2 to express the precedence constraint that the task A1 should be executed before the task A2
- , the relation $≺^+$ denotes the transitive closure if there is a chain of precedence constraints $A_1 ≺ A_2 ≺ ··· ≺ A_n, for n > 1, then A_1 ≺^+ A_n$
	- We require that the precedence relation ≺ is *acyclic*:  if $A_1 ≺ A_2$ is a precedence constraint, then we cannot have the constraint $A_2 ≺ A_1$.
	- $A_1 ≺^+ A_2$, then the output variables written by $A_2$ must await the input variables read by $A_1$
	- We write y  x if the output variable y awaits the input variable x according to the precedence constraints ≺ over the tasks
![[Pasted image 20240130164241.png]]
Task Graphs and Await Dependencies
For a synchronous reactive component $C$ with input variables $I$, output variables $O$, and state variables $S$, a task-graph description of the reactions using a set $L$ of local variables consists of a set of tasks and a binary precedence relation $\prec$ over these tasks. Each task $A$ has a read-set $R \subseteq I \cup S \cup O \cup L$, a write-set $W \subseteq O \cup S \cup L$, and an update description Update with $[[$ Update]] $\subseteq Q_R \times Q_W$ such that:
1. The precedence relation $\prec$ is acyclic.
2. Each output variable belongs to the write-set of exactly one task.
3. If an output or a local variable $y$ belongs to the read-set of a task $A$, then there exists a task $A^{\prime}$ such that $y$ is in the write-set of $A^{\prime}$ and $A^{\prime} \prec^{+} A$.
4. If a state or a local variable $x$ belongs to the write-set of a task $A$ and also to either the read-set or write-set of a different task $A^{\prime}$, then either $A \prec^{+} A^{\prime}$ or $A^{\prime} \prec^{+} A$.

For an output variable $y$ and an input variable $x, y$ awaits $x$ (also written $y \succ x$ ), precisely when for the unique task $A$, such that $y$ belongs to the write-set of $A$, either $x$ belongs to the read-set of $A$, or there exists a task $A^{\prime}$ such that $A^{\prime} \prec^{+} A$ and $x$ belongs to the read-set of $A^{\prime}$.
## Deterministic Tasks:
A task A with read-set R, write-set W, and update description Update is said to be deterministic if for every valuation s over R, there exists a unique valuation t over W such that (s, t) ∈ $[[Update]]$. Thus, given values for the read variables, a deterministic task assigns unique values to the variables it writes.’
- If a component has a single initial state and all the tasks in the task-graph description of reactions are deterministic, then the component must be deterministic. This is because the requirements on what constitutes a legal precedence relation ensure that the schedule does not affect the result of executing tasks.
## Input-Enabled Tasks:
An update task A with read-set R, write-set W, and update description Update is said to be input-enabled if for every valuation s over R, there exists at least one valuation t over W such that (s, t) ∈ $[[Update]]$. Thus, given values for the read variables, an input enabled task produces at least one result. 
- Now consider a component with a task-graph description of its reactions so that all the tasks are input enabled. Given a state and an input, we can execute all the update tasks in an order consistent with the precedence constraints. Since each task is input-enabled, there is a way to progress at every step, and thus the component can produce at least one reaction. Thus, such a component is input-enabled.
