---
title: "Unit 1"
---

### lecture 1
[video](https://ocw.mit.edu/courses/6-1200j-mathematics-for-computer-science-spring-2024/resources/61200-sp24-lecture01-2024feb06_mp4/)
[textbook](https://courses.csail.mit.edu/6.042/spring18/mcs.pdf) sections 1.0–1.7, 3.1–3.3, 3.6

a mathematical proof is a verification of a *==proposition==* by a chain of *==logical deductions==* from a base set of *==axioms==*.

a ==proposition== is a statement that is true or false.
- "Today is Tuesday"
- "Today is Thursday"
- 2 + 3 = 5
- 2 + 3 = 7

a ==predicate== is a proposition that depends on variables, like a parameterized proposition. the statement "$p$ is prime" is NOT a proposition because it is incomplete information. What $p$ are we talking about?

question: is this expression a predicate or proposition?
- $\forall n \in \mathbb{N}(n^2+n+41$ is prime$)$ 

predicates are like equations whose variables have not been filled in yet. this (n^2+n+41$ is prime$)$ is a predicate. we don't know if this is true or false because we don't know what n is. The $\forall n \in \mathbb{N}$ or "for all n in the natural numbers" transforms this into a proposition. we know what n is.

question: is $\forall n \in \mathbb{N}(n^2+n+41$ is prime$)$ true or false?

start with 0, and calculate up. turns out for $n = 40$, $n^2+n+41$ is not prime. 40 is in $\mathbb{N}$, so it is false.

Goldbach's Conjecture says every even number greater than 2 is the sum of two primes. ==Conjecture== means that we do not know if it is true.

consider A and B to be propositions.

==not==

| A   | not A, $\neg A$, and $\overline{A}$ |
| --- | ----------------------------------- |
| T   | F                                   |
| F   | T                                   |
==operators==

| A   | B   | A AND B, $A \land B$ | A OR B, $A \lor B$ | A XOR B | A NAND B |
| --- | --- | -------------------- | ------------------ | ------- | -------- |
| T   | T   | T                    | T                  | F       | F        |
| F   | T   | F                    | T                  | T       | T        |
| T   | F   | F                    | T                  | T       | T        |
| F   | F   | F                    | F                  | F       | T        |

==implication==

| A   | B   | A implies B, $A \rightarrow B$, if A then B |
| --- | --- | ------------------------------------------- |
| T   | T   | T                                           |
| F   | T   | T                                           |
| T   | F   | F                                           |
| F   | F   | T                                           |
A does not cause B. they exist independently. A is either true or false. B is either true or false. A implies B is either true or false. once we know whether A and B are true or false, we know whether if A implies B is true or false. for example, x < 3 implies x < 4.

note: $(A \rightarrow B) = (B \lor\neg A)$. A implies B is an equivalent expression to B or not A. the operators interact.

| A   | B   | $A \rightarrow B$ | $B \lor\neg A$ |
| --- | --- | ----------------- | -------------- |
| T   | T   | T                 | T              |
| F   | T   | T                 | T              |
| T   | F   | F                 | F              |
| F   | F   | T                 | T              |

 take $A \rightarrow B$ as the base expression:
  - $\neg A \rightarrow \neg B$ is the "==inverse=="
 - $B \rightarrow A$ is the "==converse=="
 - $\neg B \rightarrow \neg A$ is the "==contrapositive=="

| A   | B   | $A \rightarrow B$ | $\neg A \rightarrow \neg B$ | $B \rightarrow A$ | $\neg B \rightarrow \neg A$ |
| --- | --- | ----------------- | --------------------------- | ----------------- | --------------------------- |
| T   | T   | T                 | T                           | T                 | T                           |
| F   | T   | T                 | F                           | F                 | T                           |
| T   | F   | F                 | T                           | T                 | F                           |
| F   | F   | T                 | T                           | T                 | T                           |

the contrapositive of any expression is equivalent to itself.
notice that $A \rightarrow B$ and the contrapositive $\neg B \rightarrow \neg A$ are equivalent expressions.
notice that $\neg A \rightarrow \neg B$ and its contrapositive $B \rightarrow A$ are also equivalent expressions.

a ==set== is a collection of objects. order does not matter. repeats do not matter.
A = $\{6,1,2,0\} = \{2,1,6,0\} = \{6,1,2,0,0\}$

set examples:
- natural numbers $\mathbb{N} = \{0, 1, 2, 3, \dots\}$
- integers $\mathbb{A} = \{-3, -2, -1, 0, 1, 2, 3, \dots\}$
- rational numbers $\mathbb{Q}$ 
- real numbers $\mathbb{N}$
- complex numbers $\mathbb{N}$
-  empty set $\emptyset$. it is a subset of all sets but not an element of all sets.

question: is $3 \in B$?
- B = $\{2,\{3,4\},\emptyset\}$
no, $\{ 3,4 \}$ is in B.

$A \subseteq B$ means that A is a ==subset or equal to== B. all elements of A are in the elements of B, and B may contain more.

questions:
- $\{2,1\} \subseteq A$? yes, check if 2 and 1 are in A.
- $\emptyset \subseteq A$? yes, since there are no elements to check, nothing violates the condition.

operators:
- ==union== = $A \cup B = \{6,1,2,0, \{3,4\},\emptyset\}$. Combine together all elements of A and B.
- ==intersection== = $A\cap B = \{ 2 \}$. Only keep elements present in both A and B.
- ==difference== = $A - B$ or $A\textbackslash B = \{6,1,0\}$. Take away any elements in B from elements in A.

set builder notation:
- { $n \in \mathbb{N}$ | isprime($n$) } is the subset of natural numbers that satisfy the predicate isprime

==tuples== is a collection of elements. order matters. repeats matters.
$(6,1,2,0) \neq (2,1,6,0) \neq (6,1,2,0,0)$

an ==axiom/postulate== is a proposition we assume is true. pretty much, you can always assume whatever you want and make a theory from it, but that's not interesting.

a set of axioms is *consistent* when you can't prove both $A$ and $\neg A$. if proven, then by principle of explosion, everything becomes provable (not good for interesting theories).

a set of axioms is *complete* when every statement expressible in the system is either provable or refutable, so for every $A$ either $A$ or $\neg A$ is provable.

Gödel's Incompleteness Theorem states any consistent formal axiomatized system is incomplete. This means there are expressions that are true in standard math that are not provable in the system.

For class, the axioms that can be assumed roughly encompass high school math. "The product of two even numbers is even. I know this from high school."