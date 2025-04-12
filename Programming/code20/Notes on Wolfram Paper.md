
# Cellular Automatons
## CA Definition
All possible initial CA states: $\Sigma$
Transition rule: $\Phi$
Language of a certain step: $\Omega^t$

# Regular Languages
Language: a replacement rule for symbols
- terminal symbols are $s_i \in S$
- intermediary symbols are $u_i \in U$

## Regular Languages as Finite Automata
Regular languages can be modeled by a finite automata:

The arcs taken by the finite automata represent the input state, and the accumulation of the notes traversed represent the output state. The arrangement of nodes and arcs defines the language

### Example
Take the language where $U = \{a, b\}, S = \{A, B\}$ and valid words start with some number of a's and then have some nonzero number of b's. 
`aabbb` is a valid word.

This automaton represents the language:
```
(Start at A)

 ___a___
 |     |
(A) <--+
 |
 b
 |
 V
(B) <--+
 |     |
 +--b--+
```

An input state corresponds to a path taken through that language. For example, starting at A and taking the arc labeled 'a', then taking the path labeled 'a', then taking the path labeled 'b', then taking the path labeled 'b', then taking the path labeled 'b'. Listing the nodes passed through, one gets AABBB, which is indeed the correct output state.

## Definitions
Entropy == exponential rate of increase of number of non-empty words == log(max(eigenvalues of state transition matrix))

### State Transition Matrix
Using the above example, the transition matrix is:
$$
\begin{bmatrix}
A & B\\
B & H
\end{bmatrix}
$$
where $A = [1, 0]$, and $B = [0, 1]$, and H is halt. Unit vectors represent each node

I THINK????

### Regex
`((1*)(0*))*` represents all bitstrings

## Complexity
By the Myhill-Nerode theorem, one can always find a simplest finite automata for a given language.

Let $\Xi$ represent the minimum number of nodes (i.e. "complexity") in the finite automata graph of a language.

$\Xi^t$ is the complexity of $\Omega^t$, and grows rapidly with t for class 3 and 4 automata.

# Cellular Automata
Up to page 24

$\Omega^0 = \Sigma$
$\Omega^t$ is regular.

### Example
Elementary rule 76:
![[Pasted image 20250408141358.png]]

$a_i^1$ depends on starting states $a_{i-1}^0, a_{i}^0, a_{i+1}^0$
$a_{i+1}^1$ depends on starting states $a_{i}^0, a_{i+1}^0, a_{i+2}^0$
So both $a_i^1$ and $a_{i+1}^1$ depend on $a_i^0$ and $a_{i+1}^0$

Construct a graph $g$ from with nodes of $(a_i^0, a_{i+1}^0)$ with connections between sequential pairs. e.g. $$(a_1^0, a_2^0) \to (a_2^0, a_3^0)$$
This is isomorphic to a DeBruijn Graph, by replacing all $(a_i, a_i+1)$ with $(a_0 \ldots a_i+1)$

Thus, a traversable list of nodes (i.e. a path) through $g$ represents an initial condition for the cellular automaton denoted $A^0$, and the list of arcs taken represent the application of a step $A^1$.

![[20250409_112512.jpg]]


