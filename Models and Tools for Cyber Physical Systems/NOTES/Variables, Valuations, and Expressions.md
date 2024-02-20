the Boolean expression x? meaning x is present
# typed variables
**nat** denoting the set of natural numbers.
**int** denoting the set of integers.
**real** denoting the set of real numbers
**bool** denoting the set of Boolean values {0, 1}.
**enumerated type** contains a finite number of symbolic constants; an example of such a type is the set {on, off } with two values

- Given a set V of typed variables, a valuation over V is a type-consistent assignment to all the variables in V . That is, a valuation over V is a function q with domain V such that for each variable v ∈ V , q(v) is a value belonging to the type of v.
- We use QV to denote the set of all valuations over V . For example, if V contains two variables, the variable x of type bool and variable y of type nat, then a valuation q assigns a Boolean value to x and a natural number to y, and the set QV contains all such possible valuations. 

# Local variables
The reaction description can also use local variables, that is, auxiliary variables used to store results of intermediate computation.
This means that if the **state variables** are local the **output** can not uses those.

# Logical operations
**Negation** ¬: the expression ¬ e evaluates to 1 precisely when e evaluates to 0;
**Conjunction** (∧): the expression e1∧e2 evaluates to 1 precisely when both e1 and e2 evaluate to 1;
**Disjunction** (∨): the expression e1 ∨ e2 evaluates to 1 precisely when at least one of e1 or e2 evaluates to 1.
**Implication** (→): the expression e1 → e2 evaluates to 1 precisely when either e1 evaluates to 0 or e2 evaluates to 1.

# Inputs, Outputs and states
$I$ is the set of inputs.
$O$ is the set of outputs.
$S$ is the set of typed states variables.
those states should be finite and disjoint from one another.
- An *input* to a *reactive component* **C** is a valuation over the set I of its *input variables*, and the set of all possible inputs is QI.
- An *output* of a *component* C is a valuation over the set O of its *output variables*, and the set of all possible outputs is QO.
- A *state* of a *component* C is a valuation over the set S of its *state variables*, and the set of its states is QS.
# Initialization
Whenever a state variable is declared, the corresponding initial values are described using an assignment.

## Partially known
Sometimes we want to specify multiple possible initial values to allow modeling of situations where initial conditions are only partially known.
For this purpose, we will use a new construct called choose, which returns an arbitrarily chosen value from its argument set. 
- For the Delay component, consider an alternative declaration for the variable x given by
- bool x := choose {0, 1}
	-  As a result, the initial value of the variable x may be either 0 or 1
- **real x := choose {z | 0 ≤ z ≤ 2}**.
	- This means that the variable x is real-valued, and its initial value can be any real number between 0 and 2.

# Update
If the component in state s, when supplied with input i, can produce output o and update its state to t, we write $$S \rightarrow T $$ Such a response is called a reaction.

## Error
- when the code tries to execute an assignment statement x := e, we expect x to be either an output variable or a state variable;
- an attempt to assign a value to an input or an undeclared variable is an error.
- if the code does not assign values to all the output variables, then this execution cannot define a valid reaction
![[Pasted image 20240130142601.png]]
