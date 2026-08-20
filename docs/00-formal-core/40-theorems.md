# ASM Theorems v1.2

## Purpose

This document defines the mathematical properties derived from the
axioms and definitions of the Formal Core of the Accounting State Model
(ASM).

A theorem is a property that follows from the formal structure of ASM.

---

## Effect Uniqueness Theorem

**Statement:**

Each Event has exactly one Effect.

**Assumptions:**

Let:

$$
e\in\mathcal{E}
$$

and:

$$
\alpha:
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
$$

**Formal expression:**

For every:

$$
e\in\mathcal{E}
$$

there exists a unique:

$$
d\in\Delta\mathcal{S}
$$

such that:

$$
d=\alpha(e)
$$

**Proof sketch:**

By definition, $\alpha$ is a function.

A function assigns exactly one output to each input.

Therefore:

$$
\exists!d\in\Delta\mathcal{S}
$$

holds.

**Conclusion:**

An Event has a uniquely defined Effect.

---

## Effect and Transition Separation Theorem

**Statement:**

Effect and State Transition are different mathematical concepts.

**Formal expression:**

Effect:

$$
\alpha:
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
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

**Proof sketch:**

The Effect Function maps an Event into a State change.

The Transition Function applies that State change to a current State.

Therefore:

$$
\alpha\neq\delta
$$

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

## State Transition Determinacy Theorem

**Statement:**

Given a State and an Effect, a deterministic Transition Function
produces exactly one next State.

**Assumptions:**

Let:

$$
S_t\in\mathcal{S}
$$

and:

$$
\alpha(e)\in\Delta\mathcal{S}
$$

**Formal expression:**

There exists a unique:

$$
S_{t+1}\in\mathcal{S}
$$

such that:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

**Proof sketch:**

Since:

$$
\delta:
\mathcal{S}
\times
\Delta\mathcal{S}
\rightarrow
\mathcal{S}
$$

is a function, every input pair:

$$
(S_t,\alpha(e))
$$

has exactly one output.

**Conclusion:**

A deterministic ASM Transition produces a unique resulting State.

---

## Event Sequence Reconstruction Theorem

**Statement:**

Given an initial State and fixed transition rules, an ordered Event
sequence determines the resulting State.

**Assumptions:**

Let:

$$
H_t
=
((e_1,t_1),(e_2,t_2),\dots,(e_n,t_n))
$$

and:

$$
S_0\in\mathcal{S}
$$

with fixed:

$$
\alpha
$$

and:

$$
\delta
$$

**Formal expression:**

$$
S_n
=
\delta(
\dots
\delta(
\delta(
S_0,\alpha(e_1)
),
\alpha(e_2)
)
\dots,
\alpha(e_n)
)
$$

**Proof sketch:**

By repeated application of:

$$
S_{i+1}
=
\delta(S_i,\alpha(e_i))
$$

the final State is obtained.

**Conclusion:**

History contains sufficient information to reconstruct State when the
initial State and transition rules are known.

---

## History-State Mapping Theorem

**Statement:**

State is a derived object generated from History.

**Assumptions:**

Under fixed:

- Initial State
- Effect Function
- Transition Function

there exists:

$$
G:
\mathcal{H}
\rightarrow
\mathcal{S}
$$

such that:

$$
S_t=G(H_t)
$$

**Proof sketch:**

History contains ordered Events.

Events generate Effects.

Effects generate State transitions.

Therefore History determines the resulting State under fixed rules.

**Conclusion:**

State is not a primitive record of Events.

State is derived from accumulated History.

---

## State Equivalence Theorem

**Statement:**

Different Histories may generate the same State.

**Formal expression:**

There may exist:

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

**Proof sketch:**

The State Generation Function maps History into State.

This mapping does not necessarily preserve all information contained in
History.

Therefore, different Histories may produce the same State.

**Conclusion:**

State does not uniquely identify the past History.

---

## Multiple Representation Theorem

**Statement:**

The same underlying ASM information may generate different
Representations.

**Assumptions:**

Let:

$$
Q_1,Q_2\in\mathcal{Q}
$$

where:

$$
Q_1\neq Q_2
$$

**Formal expression:**

There exist:

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

**Proof sketch:**

Each Task defines its own Representation Function.

Therefore the output depends on the selected Task.

**Conclusion:**

A single ASM model may support multiple purpose-dependent
Representations.

---

## Representation Compression Theorem

**Statement:**

A Representation may omit information contained in the underlying
History.

**Formal expression:**

There may exist:

$$
H_1,H_2\in\mathcal{H}
$$

such that:

$$
H_1\neq H_2
$$

and:

$$
F_Q(X_1)=F_Q(X_2)
$$

**Proof sketch:**

A Representation Function maps information into a
Task-dependent Representation Space.

The mapping does not necessarily preserve all information.

**Conclusion:**

Representations are purpose-dependent abstractions.

---

## Constraint Preservation Theorem

**Statement:**

Valid State transitions preserve State Constraints.

**Assumptions:**

Let:

$$
\kappa:
\mathcal{S}
\rightarrow
\mathbb{R}
$$

be a Constraint Function.

Assume:

$$
\kappa(S_t)=0
$$

and:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

is a valid transition.

**Formal expression:**

Then:

$$
\kappa(S_{t+1})=0
$$

**Proof sketch:**

By the Constraint Preservation Principle, valid transitions maintain
required invariants.

**Conclusion:**

Constraints act as invariants of valid State transitions.

---

## Theorem Summary

| Theorem | Meaning |
| --- | --- |
| Effect Uniqueness Theorem | Each Event has one Effect |
| Effect and Transition Separation Theorem | Change and application are distinct |
| State Transition Determinacy Theorem | Deterministic transitions have unique results |
| Event Sequence Reconstruction Theorem | Events reconstruct State |
| History-State Mapping Theorem | State is derived from History |
| State Equivalence Theorem | Different Histories may produce the same State |
| Multiple Representation Theorem | One model supports multiple views |
| Representation Compression Theorem | Representations may omit information |
| Constraint Preservation Theorem | Valid transitions preserve invariants |

---

## Summary

ASM derives the following structure:

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

with State transition:

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
ASM\ is\ a\ constrained\ event-driven\ state\ transition\ framework
}
$$
