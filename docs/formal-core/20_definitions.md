# ASM Definitions v1.0

## Purpose

This document defines the fundamental concepts of the Formal Core of the
Accounting State Model (ASM).

The definitions specify the mathematical objects used in ASM.

Domain-specific interpretations are introduced in higher layers.

---

## Reality

**Definition:**

Reality is the domain containing objects, activities, and changes that
exist independently of the ASM model.

**Symbol:**

$$
\mathcal{R}
$$

**Role:**

Reality is the source from which Evidence is obtained.

---

## Evidence

**Definition:**

Evidence is observable information obtained from Reality.

**Symbol:**

$$
\mathcal{Z}
$$

**Formal relationship:**

$$
Obs\subseteq\mathcal{R}\times\mathcal{Z}
$$

**Meaning:**

Evidence is not Reality itself.

$$
Evidence\neq Reality
$$

Evidence is an observation of Reality.

---

## Event

**Definition:**

An Event is an occurrence that represents a meaningful change in the
modeled system.

**Symbol:**

$$
e
$$

**Formal expression:**

$$
e\in\mathcal{E}
$$

**Meaning:**

An Event is not a State.

An Event represents the cause of a transition.

---

## Interpretation

**Definition:**

Interpretation is the process that transforms Evidence into Events using
Policies and Parameters.

**Symbol:**

$$
I
$$

**Formal expression:**

$$
I:
\mathcal{Z}
\times
\Theta
\times
\mathcal{M}
\rightarrow
\mathcal{E}
$$

**Meaning:**

The same Evidence may produce different Events depending on the
interpretation context.

---

## Policy

**Definition:**

A Policy is a rule system used when interpreting Evidence.

**Symbol:**

$$
\theta
$$

**Formal expression:**

$$
\theta\in\Theta
$$

---

## Parameter

**Definition:**

A Parameter is an additional value or assumption used during
Interpretation.

**Symbol:**

$$
m
$$

**Formal expression:**

$$
m\in\mathcal{M}
$$

---

## History

**Definition:**

History is an ordered sequence of Events and their associated times.

**Symbol:**

$$
H(t)
$$

**Formal expression:**

$$
H(t)\in(\mathcal{E}\times T)^*
$$

or:

$$
H(t)=((e_1,t_1),(e_2,t_2),\dots,(e_n,t_n))
$$

where:

$$
e_i\in\mathcal{E}
$$

and:

$$
t_i\in T
$$

**Meaning:**

History preserves the sequence of Events.

---

## Effect

**Definition:**

Effect is the state change produced by an Event.

**Symbol:**

$$
\alpha(e)
$$

**Formal expression:**

$$
\alpha:
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
$$

and:

$$
\alpha(e)=\Delta S
$$

**Meaning:**

Effect describes how an Event changes the State.

The fundamental relationship is:

$$
Event
\rightarrow
Effect
\rightarrow
State
$$

---

## State

**Definition:**

State is the condition of the modeled system at a given time.

**Symbol:**

$$
S_t
$$

**Formal expression:**

$$
S_t\in\mathcal{S}
$$

**Meaning:**

State represents information required to describe the current condition
of the system.

---

## State Transition

**Definition:**

A State Transition is a change from one State to another caused by an
Event.

**Symbol:**

$$
\delta
$$

**Formal expression:**

$$
S_{t+1}
=
\delta(S_t,e)
$$

**Meaning:**

The transition function determines the next State from the current State
and Event.

---

## State Generation

**Definition:**

State Generation is the transformation from History into a State.

**Symbol:**

$$
G
$$

**Formal expression:**

$$
G:
\mathcal{H}
\rightarrow
\mathcal{S}
$$

such that:

$$
S_t=G(H(t))
$$

**Meaning:**

A State is a representation derived from accumulated History.

---

## Representation

**Definition:**

Representation is a transformation of History into information suitable
for a specific purpose.

**Symbol:**

$$
F_Q
$$

**Formal expression:**

$$
F_Q:
\mathcal{H}
\rightarrow
\mathcal{Y}_Q
$$

where:

$$
Q\in\mathcal{Q}
$$

**Meaning:**

Different Tasks may require different representations of the same
History.

---

## Task

**Definition:**

A Task is the purpose that determines what information is required.

**Symbol:**

$$
Q
$$

**Formal expression:**

$$
Q\in\mathcal{Q}
$$

---

## Constraint

**Definition:**

A Constraint is a condition that defines valid States.

**Symbol:**

$$
C
$$

**Formal expression:**

$$
C:
\mathcal{S}
\rightarrow
\mathbb{R}
$$

A valid State satisfies:

$$
C(S_t)=0
$$

---

## Valid Transition

**Definition:**

A Valid Transition is a State Transition that preserves required
Constraints.

**Formal expression:**

$$
C(S_t)=0
\land
Valid(e)
\Rightarrow
C(S_{t+1})=0
$$

where:

$$
S_{t+1}=\delta(S_t,e)
$$

---

## Formal Core Summary

The fundamental structure of ASM is:

$$
Reality
\rightarrow
Evidence
\rightarrow
Event
\rightarrow
Effect
\rightarrow
State
\rightarrow
Representation
$$

The mathematical structure is:

$$
\mathcal{R}
\rightarrow
\mathcal{Z}
\rightarrow
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
\rightarrow
\mathcal{S}
\rightarrow
\mathcal{Y}_Q
$$
