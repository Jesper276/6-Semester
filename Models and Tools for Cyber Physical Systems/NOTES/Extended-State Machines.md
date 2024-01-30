**Extended State Machines** the modes of the machine is augmented with additional state variables
## state-machine notation
- **mode**: is a state variable, ranging over an enumerated type.
- **mode-switches**: A mode-switch is depicted as an edge between two modes and has an associated guard-condition and a code fragment to update variables
- **Guard**: is over an edge and have to be ture before continuing.
	- if  the **Guard** does not update the **state** there has to be a **?**.
- **Update**: Updates a **state variable**.