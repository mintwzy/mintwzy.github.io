---
title: 'Logic programming'
published: true
tags: ProgrammingLanguage
---

Logic programming is a programming paradigm which is largely based on formal logic. Any program written in a logic programming language is a set of sentences in logical form, expressing facts and rules about some problem domain. Major logic programming language families include Prolog, answer set programming (ASP) and Datalog. In all of these languages, rules are written in the form of clauses:

```prolog
H :- B1, …, Bn.
```

and are read declaratively as logical implications:

```prolog
H if B1 and … and Bn.
```

`H` is called the `head` of the rule and `B1, ..., Bn` is called the `body`. Facts are rules that have no body, and are written in the simplified form:

```prolog
H.
```

In the simplest case in which `H, B1, ..., Bn` are all atomic formulae, these clauses are called definite clauses or Horn clauses. However, there are many extensions of this simple case, the most important one being the case in which conditions in the body of a clause can also be negations of atomic formulas. Logic programming languages that include this extension have the knowledge representation capabilities of a non-monotonic logic.

In ASP and Datalog, logic programs have only a declarative reading, and their execution is performed by means of a proof procedure or model generator whose behaviour is not meant to be controlled by the programmer. However, in the Prolog family of languages, logic programs also have a procedural interpretation as goal-reduction procedures:

```prolog
to solve H, solve B1, and ... and solve Bn.
```

Consider the following clause as an example:

```prolog
fallible(X) :- human(X).
```

based on an example used by Terry Winograd to illustrate the programming language Planner. As a clause in a logic program, it can be used both as a procedure to test whether X is fallible by testing whether X is human, and as a procedure to find an X which is fallible by finding an X which is human. Even facts have a procedural interpretation. For example, the clause:

```prolog
human(socrates).
```

can be used both as a procedure to show that socrates is human, and as a procedure to find an X that is human by "assigning" socrates to X.

The declarative reading of logic programs can be used by a programmer to verify their correctness. Moreover, logic-based program transformation techniques can also be used to transform logic programs into logically equivalent programs that are more efficient. In the Prolog family of logic programming languages, the programmer can also use the known problem-solving behaviour of the execution mechanism to improve the efficiency of programs.

## Reference

- [https://en.wikipedia.org/wiki/Logic_programming](https://en.wikipedia.org/wiki/Logic_programming)