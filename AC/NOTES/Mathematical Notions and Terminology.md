## SETS
- *sets* can contain **any type**
- The objects in a set are called its *elements* or *member*
- The order of describing a *set* doesn’t matter, nor does repetition of its members
- A is a *subset* of B, written $A ⊆ B$, if every member of A also is a member of $B$
- empty set is written ∅
- A *set* with one member is sometimes called a *singleton set*, and a *set* with two members is called an *unordered pair*.
- the **union** of A and B, written $A∪B$

- the power set of A is the set of all subsets of A. If A is the set {0, 1}, the power set of A is the set { ∅, {0}, {1}, {0, 1} }. The set of all ordered pairs whose elements are 0s and 1s is { (0, 0), (0, 1), (1, 0), (1, 1) }.

- If A and B are two sets, the Cartesian product or cross product of A and B, written A × B, is the set of all ordered pairs wherein the first element is a member of A and the second element is a member of B

## cross product

If $\begin{aligned} A=\{1,2\} \text { and } B & =\{x, y, z\} \\ A \times B & =\{(1, x),(1, y),(1, z),(2, x),(2, y),(2, z)\} .\end{aligned}$ 
### multiset
- If we do want to take the number of occurrences of members into account
### infinite set
- contains infinitely many elements

## SEQUENCES 
- A sequence of objects is a list of these objects in some order
- repetition does matter in a sequence

## TUPLES
Finite sequences often are called **tuples**
A sequence with **k** elements is a **k-tuple**

# FUNCTIONS AND RELATIONS
A function also is called a mapping, and, if  $f(a) = b$, we say that **f maps a to b**
- The set of possible inputs to the function is called its domain. The outputs of a function come from a set called its range. The notation for saying that f is a function with domain D and range R is f : D−→R

GRAPHS
An **undirected graph**, or simply a graph, is a set of points with lines connecting some of the points. 
- The points are called nodes or vertices, and the lines are called edges.
- In a directed graph, we represent an edge from i to j as a pair (i, j). The formal description of a directed graph G is (V, E), where V is the set of nodes and E is the set of edges.
# STRINGS AND LANGUAGES
A string over an alphabet is a finite sequence of symbols from that alphabet, usually written next to one another and not separated by commas. If $Σ1 = {0,1}$, then $01001$ is a string over $Σ1$
- the length of w, written  $|w|$, is the number of symbols that it contains
- The string of length zero is called the empty string and is written ε

# BOOLEAN LOGIC
- ∨ is OR
- ∧ is AND
- EXCLUSIVE OR, or XOR, operation is designated by the ⊕ symbol and is 1 if either but not both of its two operands is 1
- The EQUAILTY operation, written with the symbol ↔, is 1 if both of its operands have the same value
- the IMPLICATION operation is designated by the symbol → and is 0 if its first operand is 1 and its second operand is 0
$$
\begin{array}{lll}
0 \oplus 0=0 & 0 \leftrightarrow 0=1 & 0 \rightarrow 0=1 \\
0 \oplus 1=1 & 0 \leftrightarrow 1=0 & 0 \rightarrow 1=1 \\
1 \oplus 0=1 & 1 \leftrightarrow 0=0 & 1 \rightarrow 0=0 \\
1 \oplus 1=0 & 1 \leftrightarrow 1=1 & 1 \rightarrow 1=1
\end{array}
$$
