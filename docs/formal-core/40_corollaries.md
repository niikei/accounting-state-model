# ASM Corollaries v1.0

## Purpose

This document defines corollaries derived from the Formal Core of the
Accounting State Model (ASM).

A corollary is a consequence obtained from the axioms, definitions, and
theorems of ASM.

Domain-specific applications are introduced in higher layers.

---

## Event-driven State Corollary

**Statement:**

ASM represents a system as a sequence of Events that generate Effects and
change States.

**Formal expression:**

For:

$$
e\in\mathcal{E}
$$

there exists:

$$
\alpha(e)\in\Delta\mathcal{S}
$$

and:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

**Derivation:**

From the Effect Generation Principle and Effect Application Principle.

**Conclusion:**

ASM is an event-driven state transition model.

---

## Event Sourcing Corollary

**Statement:**

ASM has the structural property that State can be derived from accumulated
Events.

**Formal expression:**

Given:

$$
H(t)=((e_1,t_1),\dots,(e_n,t_n))
$$

the resulting State is:

$$
S_t=G(H(t))
$$

where:

$$
S_{i+1}
=
\delta(S_i,\alpha(e_i))
$$

**Derivation:**

History stores Events.

Each Event produces an Effect.

Each Effect produces a State transition.

**Conclusion:**

ASM supports reconstruction of State from Event History.

---

## Audit Trail Corollary

**Statement:**

Every State change can be traced back to an Event.

**Formal expression:**

For a transition:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

there exists an Event:

$$
e\in\mathcal{E}
$$

that generated the applied Effect.

**Derivation:**

By the Effect Generation Principle:

$$
\alpha:
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
$$

**Conclusion:**

ASM naturally preserves the causal path of State changes.

---

## Effect-based Change Corollary

**Statement:**

ASM separates the description of change from the mechanism that applies
change.

**Formal expression:**

Effect:

$$
\alpha(e)\in\Delta\mathcal{S}
$$

Transition:

$$
\delta:
\mathcal{S}
\times
\Delta\mathcal{S}
\rightarrow
\mathcal{S}
$$

**Derivation:**

From the Effect and Transition Separation Theorem.

**Conclusion:**

The same Effect concept can be applied by different transition mechanisms.

---

## Projection Corollary

**Statement:**

One History can generate multiple representations.

**Formal expression:**

For:

$$
Q_1,Q_2\in\mathcal{Q}
$$

there exist:

$$
F_{Q_1}
:
\mathcal{H}
\rightarrow
\mathcal{Y}_{Q_1}
$$

and:

$$
F_{Q_2}
:
\mathcal{H}
\rightarrow
\mathcal{Y}_{Q_2}
$$

such that:

$$
F_{Q_1}(H)
\neq
F_{Q_2}(H)
$$

may hold.

**Derivation:**

From the Representation Principle.

**Conclusion:**

History is the common source of multiple views.

---

## State Compression Corollary

**Statement:**

State is a compressed representation of accumulated Events.

**Formal expression:**

Given:

$$
S_t=G(H(t))
$$

State does not necessarily contain all information in:

$$
H(t)
$$

**Derivation:**

From the Representation Compression Theorem.

**Conclusion:**

State and History are different mathematical objects.

---

## State Sufficiency Corollary

**Statement:**

A State contains sufficient information if future transitions required by a
purpose can be determined from that State.

**Formal expression:**

For a Task:

$$
Q\in\mathcal{Q}
$$

there exists:

$$
\delta_Q
$$

such that:

$$
S_{t+1}
=
\delta_Q(S_t,\alpha(e))
$$

**Derivation:**

The State preserves the information required by the transition process
for the intended purpose.

**Conclusion:**

State is not a complete History but a sufficient abstraction.

---

## Layer Extension Corollary

**Statement:**

Domain-specific models can be constructed by defining specialized State
Spaces.

**Formal expression:**

The Formal Core defines:

$$
\mathcal{S}
$$

A domain may introduce:

$$
\mathcal{S}_D
$$

with:

$$
\mathcal{S}_D
\rightarrow
\mathcal{S}
$$

**Derivation:**

The Formal Core defines the transition structure but does not restrict the
contents of State.

**Conclusion:**

Accounting and ERP models can extend ASM without changing the Formal
Core.

---

## Corollary Summary

| Corollary | Meaning |
| --- | --- |
| Event-driven State Corollary | Events generate Effects and State changes |
| Event Sourcing Corollary | State can be reconstructed from History |
| Audit Trail Corollary | State changes remain traceable |
| Effect-based Change Corollary | Change and application are separated |
| Projection Corollary | One History supports multiple views |
| State Compression Corollary | State abstracts History |
| State Sufficiency Corollary | State preserves required information |
| Layer Extension Corollary | Domain models extend the Core |
