# ASM Notation v1.2

## Purpose

This document defines the official mathematical notation used in the
Formal Core of the Accounting State Model (ASM).

All Formal Core documents MUST follow the notation defined here.

The Formal Core defines an abstract model of constrained event-driven
state transitions.

Domain-specific concepts, including accounting structures, are introduced
in higher layers.

---

## General Mathematical Convention

**Definition:**

A mathematical space is represented by a calligraphic letter.

Example:

$$
\mathcal{X}
$$

An element belonging to a space is represented by a lowercase letter.

Example:

$$
x\in\mathcal{X}
$$

A function is represented by a mapping.

Example:

$$
f:X\rightarrow Y
$$

A relation is represented as a subset of a Cartesian product.

Example:

$$
R\subseteq X\times Y
$$

---

## Time Notation

### Time Space

**Symbol:**

$$
T
$$

**Definition:**

The domain of temporal points used in ASM.

---

### Time Point

**Symbol:**

$$
t
$$

**Formal expression:**

$$
t\in T
$$

**Definition:**

A single point in the Time Space.

---

### Period

**Symbol:**

$$
\tau
$$

**Formal expression:**

$$
\tau=[t_0,t_1]\subseteq T
$$

**Definition:**

A temporal interval used to select or aggregate Events.

---

## Reality and Observation

### Reality Space

**Symbol:**

$$
\mathcal{R}
$$

**Definition:**

The space representing objects and changes that exist independently of
the ASM model.

---

### Evidence Space

**Symbol:**

$$
\mathcal{Z}
$$

**Definition:**

The space of observable information obtained from Reality.

---

### Observation Relation

**Symbol:**

$$
Obs
$$

**Formal expression:**

$$
Obs\subseteq\mathcal{R}\times\mathcal{Z}
$$

**Definition:**

The relation connecting Reality and Evidence.

---

## Event Notation

### Event Space

**Symbol:**

$$
\mathcal{E}
$$

**Definition:**

The space of Events represented in ASM.

---

### Event

**Symbol:**

$$
e
$$

**Formal expression:**

$$
e\in\mathcal{E}
$$

**Definition:**

An occurrence recognized by ASM that produces an Effect on the modeled
system.

**Meaning:**

An Event represents the causal input of a State transition.

---

## Interpretation Notation

### Policy Space

**Symbol:**

$$
\Theta
$$

**Definition:**

The space of Policies used for Interpretation.

---

### Policy

**Symbol:**

$$
\theta
$$

**Formal expression:**

$$
\theta\in\Theta
$$

**Definition:**

A rule system applied during Interpretation.

---

### Parameter Space

**Symbol:**

$$
\mathcal{M}
$$

**Definition:**

The space of Parameters or assumptions used during Interpretation.

---

### Parameter

**Symbol:**

$$
m
$$

**Formal expression:**

$$
m\in\mathcal{M}
$$

**Definition:**

A value or assumption required during Interpretation.

---

### Interpretation Function

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

**Definition:**

A function that transforms Evidence into Events according to Policies
and Parameters.

---

## History Notation

### History Space

**Symbol:**

$$
\mathcal{H}
$$

**Definition:**

The space of Event histories.

---

### History

**Symbol:**

$$
H_t
$$

**Formal expression:**

$$
H_t\in(\mathcal{E}\times T)^*
$$

**Definition:**

An ordered sequence of Events accumulated up to time $t$.

---

### Event Sequence

**Formal expression:**

$$
H_t
=
((e_1,t_1),(e_2,t_2),\dots,(e_n,t_n))
$$

where:

$$
e_i\in\mathcal{E}
$$

and:

$$
t_i\in T
$$

---

## State Notation

### State Space

**Symbol:**

$$
\mathcal{S}
$$

**Definition:**

The space of possible system States.

---

### State

**Symbol:**

$$
S_t
$$

**Formal expression:**

$$
S_t\in\mathcal{S}
$$

**Definition:**

The condition of the modeled system at time $t$.

---

### State Generation Function

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

**Definition:**

A function that generates a State from accumulated History.

The reconstructed State is:

$$
S_t=G(H_t)
$$

---

## Effect Notation

### Effect Space

**Symbol:**

$$
\Delta\mathcal{S}
$$

**Definition:**

The space of possible instantaneous changes in State.

---

### Effect Function

**Symbol:**

$$
\alpha
$$

**Formal expression:**

$$
\alpha:
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
$$

**Definition:**

A function that maps an Event to its Effect.

---

### Effect

**Symbol:**

$$
\alpha(e)
$$

**Formal expression:**

$$
\alpha(e)\in\Delta\mathcal{S}
$$

**Definition:**

The State change produced by an Event.

**Meaning:**

Effect represents what changes.

The fundamental relationship is:

$$
Event
\rightarrow
Effect
\rightarrow
State
$$

---

## Flow Notation

### Flow Space

**Symbol:**

$$
\mathcal{F}
$$

**Definition:**

The space of accumulated Effects over a period.

---

### Flow

**Formal expression:**

For a period:

$$
\tau\subseteq T
$$

Flow is:

$$
Flow(\tau)
=
\sum_{(e,t)\in H_\tau}
\alpha(e)
$$

**Definition:**

An accumulation of Effects generated during a temporal interval.

**Meaning:**

Effect represents an instantaneous change.

Flow represents accumulated changes.

Therefore:

$$
Effect
\neq
Flow
$$

---

## State Transition Notation

### State Transition Function

**Symbol:**

$$
\delta
$$

**Formal expression:**

$$
\delta:
\mathcal{S}
\times
\Delta\mathcal{S}
\rightarrow
\mathcal{S}
$$

**Definition:**

A function that applies an Effect to a State and produces a new State.

---

### State Transition

**Formal expression:**

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

**Definition:**

The next State obtained by applying the Effect generated by an Event.

---

## Representation Notation

### Task Space

**Symbol:**

$$
\mathcal{Q}
$$

**Definition:**

The space of purposes requiring information.

---

### Task

**Symbol:**

$$
Q
$$

**Formal expression:**

$$
Q\in\mathcal{Q}
$$

**Definition:**

A purpose that determines required information.

---

### Representation Space

**Symbol:**

$$
\mathcal{Y}
$$

**Definition:**

The space of representations generated for Tasks.

---

### Task-dependent Input Space

**Symbol:**

$$
\mathcal{X}_Q
$$

**Definition:**

The information space required for Task $Q$.

The input may contain History, State, or other information depending on
the Task.

---

### Task-dependent Representation Function

**Symbol:**

$$
F_Q
$$

**Formal expression:**

$$
F_Q:
\mathcal{X}_Q
\rightarrow
\mathcal{Y}_Q
$$

**Definition:**

A function that transforms Task-dependent input information into a
Representation suitable for Task $Q$.

---

## Constraint Notation

### Constraint Space

**Symbol:**

$$
\mathcal{C}
$$

**Definition:**

The space of constraints required for valid States.

---

### Constraint Function

**Symbol:**

$$
\kappa
$$

**Formal expression:**

$$
\kappa:
\mathcal{S}
\rightarrow
\mathbb{R}
$$

**Definition:**

A function that evaluates whether a State satisfies a Constraint.

---

### Valid State

**Formal expression:**

$$
\kappa(S_t)=0
$$

**Definition:**

A State satisfying required constraints.

---

## ASM Core Structure

ASM contains two related structures.

### Information Preservation Structure

$$
\mathcal{R}
\rightarrow
\mathcal{Z}
\rightarrow
\mathcal{E}
\rightarrow
\mathcal{H}
\rightarrow
\mathcal{S}
\rightarrow
\mathcal{Y}_Q
$$

---

### State Transition Structure

$$
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
\rightarrow
\mathcal{S}
$$

The transition sequence is:

$$
e
\rightarrow
\alpha(e)
\rightarrow
S_{t+1}
$$
