The basic type **event** is the enumerated type {$\top$, $\bot$}
- $\top$ denotes that the event is present 
- $\bot$ denotes that the event is absent
- We allow the event type to be parameterized by another type
- **Note:** input, output, and local variables can be of type event, a state variable cannot be of this type, as it is not meaningful to consider a state to be absent.
- By default, an **output event variable** is **absent**, that is, if the event output variable **out** is not explicitly assigned a value during a round, then its value is assumed to be ⊥.
- *Stuttering*: If the input is absent in a round, then the component is passive: the output is absent, and the state stays unchanged.
![[Pasted image 20240130153921.png]]
