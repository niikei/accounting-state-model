# ASM Corollaries v1.0

## Purpose

This document defines corollaries derived from the Formal Core of the
Accounting State Model (ASM).

A corollary is a consequence obtained from the axioms, definitions, and
theorems of ASM.

Domain-specific applications are defined in higher layers.

---

## Event Sourcing Corollary

**Statement:**

ASM has an event-oriented structure in which State is derived from a
sequence of Events.

**Formal expression:**

Given:

$$
H(t)\in(\mathcal{E}\times T)^*
$$

and:

$$
G:\mathcal{H}\rightarrow\mathcal{S}
$$

State is obtained by:

$$
S_t=G(H(t))
$$

**Derivation:**

ASM defines:

$$
Event
\rightarrow
History
\rightarrow
State
$$

Therefore, the current State can be reconstructed from accumulated
Events.

**Conclusion:**

ASM has the same structural property as event-sourced systems.

---

## Audit Trail Corollary

**Statement:**

A complete History provides traceability from State changes back to
Events.

**Formal expression:**

For:

$$
S_t=G(H(t))
$$

there exists an ordered sequence:

$$
H(t)=((e_1,t_1),\dots,(e_n,t_n))
$$

that explains the transition path.

**Derivation:**

State changes are generated through:

$$
S_{t+1}=\delta(S_t,e)
$$

Therefore each transition has a corresponding Event.

**Conclusion:**

ASM naturally supports traceable state changes.

---

## Projection Corollary

**Statement:**

Different Tasks may create different representations from the same
History.

**Formal expression:**

For:

$$
Q_1,Q_2\in\mathcal{Q}
$$

there exist:

$$
F_{Q_1}
$$

and:

$$
F_{Q_2}
$$

such that:

$$
F_{Q_1}(H)
\neq
F_{Q_2}(H)
$$

may hold.

**Derivation:**

From the Representation Principle:

$$
F_Q:
\mathcal{H}
\rightarrow
\mathcal{Y}_Q
$$

**Conclusion:**

A single History supports multiple views.

---

## State Compression Corollary

**Statement:**

A State is a compressed representation of History that preserves required
information.

**Formal expression:**

Given:

$$
S_t=G(H(t))
$$

and:

$$
S_t\in\mathcal{S}
$$

the State does not necessarily contain all information in:

$$
H(t)
$$

**Derivation:**

From the Information Loss Theorem:

$$
\exists H_1,H_2
$$

such that:

$$
H_1\neq H_2
$$

and:

$$
F_Q(H_1)=F_Q(H_2)
$$

**Conclusion:**

State and History are different objects.

---

## State Machine Corollary

**Statement:**

ASM can be represented as a state transition system.

**Formal expression:**

The transition is:

$$
\delta:
\mathcal{S}\times\mathcal{E}
\rightarrow
\mathcal{S}
$$

with:

$$
S_{t+1}
=
\delta(S_t,e)
$$

**Derivation:**

From the State Transition Principle.

**Conclusion:**

ASM is mathematically a state machine driven by Events.

---

## Separation of Event and State Corollary

**Statement:**

Events and States represent different categories of information.

**Formal expression:**

An Event:

$$
e\in\mathcal{E}
$$

produces:

$$
\alpha(e)\in\Delta\mathcal{S}
$$

which changes:

$$
S_t\in\mathcal{S}
$$

**Derivation:**

By definition:

$$
Event\neq State
$$

and:

$$
Effect=\Delta State
$$

**Conclusion:**

ASM separates causes of change from resulting conditions.

---

## Task-dependent Modeling Corollary

**Statement:**

The appropriate State representation depends on the intended Task.

**Formal expression:**

For:

$$
Q\in\mathcal{Q}
$$

there exists:

$$
F_Q
$$

such that:

$$
F_Q:
\mathcal{H}
\rightarrow
\mathcal{Y}_Q
$$

**Derivation:**

Different Tasks require different information.

**Conclusion:**

There is no single universal representation of History.

---

## Layered Extension Corollary

**Statement:**

Domain-specific models can be constructed by defining specialized State
Spaces.

**Formal expression:**

Given the Formal Core:

$$
\mathcal{S}
$$

a domain model may define:

$$
\mathcal{S}_D
$$

where:

$$
\mathcal{S}_D
\subseteq
\mathcal{S}
$$

or:

$$
\mathcal{S}_D
\rightarrow
\mathcal{S}
$$

**Derivation:**

The Formal Core defines the structure of state transition, not the
contents of every State.

**Conclusion:**

Accounting, ERP, and other domains can extend ASM without modifying the
core.

---

## Corollary Summary

| Corollary | Meaning |
| --- | --- |
| Event Sourcing Corollary | State can be derived from Events |
| Audit Trail Corollary | State changes remain traceable |
| Projection Corollary | One History supports multiple Views |
| State Compression Corollary | State is not identical to History |
| State Machine Corollary | ASM is a transition system |
| Event-State Separation Corollary | Events and States are distinct |
| Task-dependent Modeling Corollary | Representations depend on purpose |
| Layered Extension Corollary | Domain models extend the Core |
