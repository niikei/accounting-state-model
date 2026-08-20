# ASM Axioms v1.0

## Purpose

This document defines the fundamental axioms of the Formal Core of the
Accounting State Model (ASM).

The axioms describe the assumptions required to construct the ASM
framework.

Accounting-specific interpretations are introduced in higher layers.

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

- $\mathcal{R}$ is Reality Space.
- $\mathcal{Z}$ is Evidence Space.

**Explanation:**

Reality and Evidence are different mathematical objects.

Therefore:

$$
\exists r\in\mathcal{R},
\exists z\in\mathcal{Z}
$$

such that:

$$
(r,z)\in Obs
$$

may hold.

**Consequence:**

ASM models interpreted information rather than Reality itself.

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

- $\Theta$ is Policy Space.
- $\mathcal{M}$ is Parameter Space.

**Explanation:**

An Event is not identical to Evidence.

The same Evidence may produce different Events under different
Interpretation contexts.

Formally:

$$
\exists z\in\mathcal{Z},
\exists\theta_1,\theta_2\in\Theta,
\exists m_1,m_2\in\mathcal{M}
$$

such that:

$$
(\theta_1,m_1)\neq(\theta_2,m_2)
$$

and:

$$
I(z,\theta_1,m_1)
\neq
I(z,\theta_2,m_2)
$$

may hold.

**Consequence:**

Interpretation is context-dependent.

---

## Historical Persistence Principle

**Statement:**

Events are accumulated into an ordered History.

**Formal expression:**

$$
H_t\in(\mathcal{E}\times T)^*
$$

**Explanation:**

For:

$$
t_1<t_2
$$

History grows by adding Events.

Formally:

$$
H_{t_1}\subseteq H_{t_2}
$$

under normal progression.

**Consequence:**

A change to History requires an explicit Event.

---

## Effect Generation Principle

**Statement:**

Every Event generates exactly one Effect.

**Formal expression:**

$$
\forall e\in\mathcal{E},
\exists!\alpha(e)\in\Delta\mathcal{S}
$$

where:

$$
\alpha:
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
$$

**Explanation:**

An Event represents a cause.

An Effect represents the state change produced by that cause.

The fundamental relationship is:

$$
e
\rightarrow
\alpha(e)
$$

**Consequence:**

Events and Effects are distinct mathematical objects.

---

## Effect Application Principle

**Statement:**

A State changes by applying an Effect to the current State.

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
Effect\neq Transition
$$

**Consequence:**

ASM separates state change description from state transition mechanism.

---

## State Reconstruction Principle

**Statement:**

A State can be generated from accumulated History.

**Formal expression:**

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

**Explanation:**

History contains the ordered Events required to derive the current State.

**Consequence:**

State is a derived object from History.

---

## Representation Principle

**Statement:**

A single History may generate multiple representations according to
different Tasks.

**Formal expression:**

For:

$$
Q\in\mathcal{Q}
$$

there exists:

$$
F_Q:
\mathcal{H}
\rightarrow
\mathcal{Y}_Q
$$

**Explanation:**

Different Tasks require different information.

Therefore:

$$
Q_1\neq Q_2
$$

may produce:

$$
F_{Q_1}(H_t)
\neq
F_{Q_2}(H_t)
$$

**Consequence:**

Representation depends on purpose.

---

## Constraint Preservation Principle

**Statement:**

Valid State transitions preserve required Constraints.

**Formal expression:**

Let:

$$
\kappa:\mathcal{S}\rightarrow\mathbb{R}
$$

be a Constraint Function.

If:

$$
\kappa(S_t)=0
$$

and:

$$
Valid(e)
$$

then:

$$
\kappa(S_{t+1})=0
$$

where:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
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
| Representation Principle | History generates Task-dependent Views |
| Constraint Preservation Principle | Valid transitions preserve invariants |
