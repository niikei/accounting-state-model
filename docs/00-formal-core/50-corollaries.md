# ASM Corollaries v1.2

## Purpose

This document defines corollaries derived from the Formal Core of the
Accounting State Model (ASM).

A corollary is a consequence obtained from the axioms, definitions, and
theorems of ASM.

Domain-specific applications are introduced in higher layers.

---

## Event-driven State Corollary

**Statement:**

ASM represents a system as Events that generate Effects and change
States.

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

An Event generates an Effect.

The Effect is applied through the State Transition Function.

**Conclusion:**

ASM represents systems as event-driven state transition systems.

---

## Event Sourcing Corollary

**Statement:**

ASM has the structural property that State can be reconstructed from
accumulated Events.

**Formal expression:**

Given:

$$
H_t
=
((e_1,t_1),(e_2,t_2),\dots,(e_n,t_n))
$$

the resulting State is:

$$
S_t=G(H_t)
$$

under fixed:

- Initial State
- Effect Function
- Transition Function

**Derivation:**

History stores Events.

Each Event generates an Effect.

Each Effect produces a State Transition.

**Conclusion:**

ASM supports reconstruction of State from Event History.

---

## Audit Trail Corollary

**Statement:**

Every State change can be traced back to an Event.

**Formal expression:**

For:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

there exists:

$$
e\in\mathcal{E}
$$

that generated the applied Effect.

**Derivation:**

From the Effect Generation Principle:

$$
\alpha:
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
$$

Each Effect has a causal Event.

**Conclusion:**

ASM preserves the causal trace of State changes.

---

## Causality Preservation Corollary

**Statement:**

ASM preserves the causal relationship between Events and State changes.

**Formal expression:**

$$
e
\rightarrow
\alpha(e)
\rightarrow
S_{t+1}
$$

**Derivation:**

An Event generates an Effect.

The Effect is applied through the Transition Function.

Therefore State changes have identifiable causal origins.

**Conclusion:**

ASM provides explainable State transitions.

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

Effect defines what changes.

Transition defines how the change is applied.

**Conclusion:**

ASM separates:

$$
what\ changes
$$

from:

$$
how\ the\ change\ is\ applied
$$

---

## Projection Corollary

**Statement:**

One underlying ASM model can generate multiple Representations.

**Formal expression:**

For:

$$
Q_1,Q_2\in\mathcal{Q}
$$

there exist:

$$
F_{Q_1}:
\mathcal{X}_{Q_1}
\rightarrow
\mathcal{Y}_{Q_1}
$$

and:

$$
F_{Q_2}:
\mathcal{X}_{Q_2}
\rightarrow
\mathcal{Y}_{Q_2}
$$

such that:

$$
F_{Q_1}(X)
\neq
F_{Q_2}(X)
$$

may hold.

**Derivation:**

From the Representation Principle.

Each Task defines a different Representation Function.

**Conclusion:**

A single underlying system supports multiple purpose-dependent views.

---

## Representation Separation Corollary

**Statement:**

A Representation is not identical to the underlying State.

**Formal expression:**

In general:

$$
F_Q(X_Q)\neq S_t
$$

**Derivation:**

A Representation is generated for a specific Task.

It preserves information required for that Task but may omit other
information.

**Conclusion:**

Reports, views, and documents are projections of State, not State itself.

---

## State Abstraction Corollary

**Statement:**

State is a derived abstraction of accumulated History.

**Formal expression:**

$$
S_t=G(H_t)
$$

but there may exist:

$$
H_1,H_2\in\mathcal{H}
$$

such that:

$$
H_1\neq H_2
$$

and:

$$
G(H_1)=G(H_2)
$$

**Derivation:**

From the State Equivalence Theorem.

The State Generation Function does not necessarily preserve all
historical information.

**Conclusion:**

State represents the current condition, not the complete historical path.

---

## State Sufficiency Corollary

**Statement:**

A State is sufficient when it preserves information required for future
State transitions.

**Formal expression:**

For:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

the State contains the information required to determine future
transitions under the ASM model.

**Derivation:**

From the State Transition Determinacy Theorem.

A State does not need to contain complete History.

It only needs to contain transition-relevant information.

**Conclusion:**

State is a sufficient summary of the past for future transitions.

---

## Layer Extension Corollary

**Statement:**

Domain-specific models can be constructed by defining specialized
spaces.

**Formal expression:**

The Formal Core defines:

$$
\mathcal{S}
$$

A domain may introduce:

$$
\mathcal{S}_D
$$

such that:

$$
\mathcal{S}_D
\subseteq
\mathcal{S}
$$

Similarly:

$$
\mathcal{E}_D
\subseteq
\mathcal{E}
$$

and:

$$
\Delta\mathcal{S}_D
\subseteq
\Delta\mathcal{S}
$$

**Derivation:**

The Formal Core defines general transition structures.

Domain layers specialize meanings and constraints.

**Conclusion:**

Accounting and ERP models can extend ASM without modifying the Formal
Core.

---

## Corollary Summary

| Corollary | Meaning |
| --- | --- |
| Event-driven State Corollary | Events generate Effects and State changes |
| Event Sourcing Corollary | State can be reconstructed from History |
| Audit Trail Corollary | State changes remain traceable |
| Causality Preservation Corollary | State changes preserve causal origins |
| Effect-based Change Corollary | Change and application are separated |
| Projection Corollary | One model supports multiple views |
| Representation Separation Corollary | Representations are not States |
| State Abstraction Corollary | State abstracts accumulated History |
| State Sufficiency Corollary | State preserves transition-relevant information |
| Layer Extension Corollary | Domain models extend the Core |

---

## Summary

ASM derives the following consequences:

Information preservation:

$$
Reality
\rightarrow
Evidence
\rightarrow
Event
\rightarrow
History
\rightarrow
State
\rightarrow
Representation
$$

State transition:

$$
Event
\rightarrow
Effect
\rightarrow
State
$$

Therefore:

$$
\boxed{
ASM\ provides\ a\ causal,\ reconstructable,\ and\ purpose-dependent\ state\ model
}
$$
