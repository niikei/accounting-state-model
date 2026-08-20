# ASM Axioms v1.2

## Purpose

This document defines the fundamental axioms of the Formal Core of the
Accounting State Model (ASM).

The axioms describe the assumptions required to construct the ASM
framework.

Domain-specific interpretations, including accounting concepts, are
introduced in higher layers.

---

## Observation Principle

**Statement:**

ASM does not directly operate on Reality.

ASM operates on Evidence obtained through Observation.

**Formal expression:**

$$
Obs\subseteq\mathcal{R}\times\mathcal{Z}
$$

where:

- $\mathcal{R}$ represents Reality Space.
- $\mathcal{Z}$ represents Evidence Space.

**Explanation:**

Reality and Evidence are different mathematical objects.

Therefore:

$$
Reality
\neq
Evidence
$$

Evidence represents an observation of Reality, not Reality itself.

**Consequence:**

ASM models interpreted information rather than Reality directly.

---

## Interpretation Principle

**Statement:**

Evidence is transformed into Events through Interpretation.

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

where:

- $\Theta$ represents Policy Space.
- $\mathcal{M}$ represents Parameter Space.

**Explanation:**

An Event is not identical to Evidence.

The same Evidence may generate different Events depending on
Interpretation context.

Formally:

$$
I(z,\theta_1,m_1)
\neq
I(z,\theta_2,m_2)
$$

may hold.

**Consequence:**

Events are interpreted representations generated from Evidence.

---

## Historical Persistence Principle

**Statement:**

Events are accumulated into an ordered History.

**Formal expression:**

$$
H_t
\in
(\mathcal{E}\times T)^*
$$

**Explanation:**

History preserves the sequence of Events.

For:

$$
t_1<t_2
$$

History satisfies:

$$
H_{t_1}
\subseteq
H_{t_2}
$$

under continuous progression.

**Consequence:**

The causal path of State changes is preserved.

---

## Effect Generation Principle

**Statement:**

Each Event generates an Effect.

**Formal expression:**

$$
\alpha:
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
$$

Therefore:

$$
\alpha(e)\in\Delta\mathcal{S}
$$

**Explanation:**

An Event represents the cause of change.

An Effect represents the State change produced by that Event.

The relationship is:

$$
Event
\rightarrow
Effect
$$

Therefore:

$$
Event
\neq
Effect
$$

**Consequence:**

ASM separates occurrence from State change.

---

## Effect Application Principle

**Statement:**

A State changes through the application of an Effect.

**Formal expression:**

$$
\delta:
\mathcal{S}
\times
\Delta\mathcal{S}
\rightarrow
\mathcal{S}
$$

and:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

**Explanation:**

The Effect describes what changes.

The Transition Function describes how the change is applied.

Therefore:

$$
Effect
\neq
Transition
$$

**Consequence:**

ASM separates change description from transition mechanism.

---

## State Reconstruction Principle

**Statement:**

A State can be reconstructed from accumulated History.

**Formal expression:**

$$
G:
\mathcal{H}
\rightarrow
\mathcal{S}
$$

such that:

$$
S_t
=
G(H_t)
$$

**Explanation:**

History contains the Events required to derive the current State.

**Consequence:**

State is a derived object generated from History.

---

## History-State Separation Principle

**Statement:**

History and State are different mathematical objects.

**Formal expression:**

There may exist:

$$
H_1,H_2\in\mathcal{H}
$$

such that:

$$
H_1\neq H_2
$$

but:

$$
G(H_1)
=
G(H_2)
$$

**Explanation:**

Different Event paths may result in the same State.

History represents the path.

State represents the current condition.

**Consequence:**

State does not replace History.

---

## Flow Accumulation Principle

**Statement:**

Flow represents accumulated Effects over a period.

**Formal expression:**

For:

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

**Explanation:**

Effect represents an instantaneous State change.

Flow represents accumulated changes over a temporal interval.

Therefore:

$$
Effect
\neq
Flow
$$

**Consequence:**

Period-based information is derived from accumulated Effects.

---

## Representation Principle

**Statement:**

A system may generate multiple Representations according to different
Tasks.

**Formal expression:**

For:

$$
Q\in\mathcal{Q}
$$

there exists:

$$
F_Q:
\mathcal{X}_Q
\rightarrow
\mathcal{Y}_Q
$$

**Explanation:**

Different Tasks require different views of the same underlying system.

Therefore:

$$
F_{Q_1}(X)
\neq
F_{Q_2}(X)
$$

may hold.

**Consequence:**

Representation depends on purpose.

---

## Constraint Preservation Principle

**Statement:**

Valid State transitions preserve required Constraints.

**Formal expression:**

Let:

$$
\kappa:
\mathcal{S}
\rightarrow
\mathbb{R}
$$

be a Constraint Function.

If:

$$
\kappa(S_t)=0
$$

and:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

then valid transitions satisfy:

$$
\kappa(S_{t+1})=0
$$

**Explanation:**

Constraints define invariant properties of valid States.

**Consequence:**

ASM preserves consistency through invariant maintenance.

---

## Axiom Summary

| Axiom | Main Concept |
| --- | --- |
| Observation Principle | Reality is accessed through Evidence |
| Interpretation Principle | Evidence is transformed into Events |
| Historical Persistence Principle | Events form persistent History |
| Effect Generation Principle | Events generate Effects |
| Effect Application Principle | Effects transform States |
| State Reconstruction Principle | History generates State |
| History-State Separation Principle | State and History are distinct |
| Flow Accumulation Principle | Effects accumulate into Flow |
| Representation Principle | Systems generate Task-dependent Views |
| Constraint Preservation Principle | Valid transitions preserve invariants |

---

## Summary

ASM is constructed from the following principles:

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
