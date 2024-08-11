### Prepositional Logic
Prepositional logic deals with statements and propositions which can only be True or False,
$$\text{let} \: \mathbb{B} = \set{False, True}$$
as well as with operators of those values such as $\neg$, $\lor$, and $\land$.

### Set Logic
Sets can be described in terms of a characteristic function, which returns whether or not an element x is contained within the set S. Let S.C be the characteristic function of S, and U be the universal set:
$$\set{x \in U \:\vert\:S.C(x) } \qquad x \in S \iff S.C(x) \qquad S.C: U \to \mathbb{B}$$
Of course, all elements x must themselves be sets. So aside from propositional logic, the following operators may also be used on elements:
$$x\in U, S\in U^P, P:x\to \mathbb{B}$$
$$\in: (x, S)\to\mathbb{B}$$
$$\exists:(x, P)\to\mathbb{B}$$
$$\forall:(x, P)\to\mathbb{B}$$
$$=: (S, T) \to \mathbb{B}$$
with the following definitions and notations:
$$x \in S := S.C(x)$$
$$\exists x \vert P := \set{x \vert P} \ne \emptyset$$
$$\forall x, P := \set{x \vert P} = \set{x|True}$$
$$S=T\::= S.C(x) \iff T.C(x)$$
For example, the statement *"S is empty"* can be written as any of the following:
$$\neg \exists x \vert x \in S \qquad \forall x, x \notin S \qquad S = \emptyset \qquad \neg S.C(x)$$

### ZF Set Theory
I am going to assume that a set can be constructed with any arbitrary characteristic function.
This leads to many of the axioms of ZF Set theory:

##### Axiom of Extensionality
Two sets are equal if they have the same elements. i.e., $=\::= \forall x, x \in S \iff x \in T$

Because the $\in$ operation is defined in terms of the characteristic function, my definition of equality is equivalent to the above definition of equality, and so my implementation of set theory agrees with this axiom.

##### Axiom of Regularity
Every set must contain a member that is disjoint with itself.

This cannot be constructed in 

etc. etc. I'm getting bored of proofs I'm moving on to implementation.


# Implementation
### Sets
```Julia
struct set
		C::Function
end

function setFromElements(elements::List)
		expr = ""
		for el in elements
				expr *= "x = $el | "
		end
		expr = [1:-3]
		return set(evalexpr(expr))
end
```


