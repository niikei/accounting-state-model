# ASM Theorems v1.0

## Purpose

This document defines the mathematical properties derived from the axioms
and definitions of the Formal Core of the Accounting State Model (ASM).

A theorem is a property that follows from the formal structure of ASM.

---

## Effect Determinacy Theorem

**Statement:**

Every Event has a uniquely defined Effect.

**Assumptions:**

Let:

$$
e\in\mathcal{E}
$$

**Formal expression:**

$$
\forall e\in\mathcal{E},
\exists!\alpha(e)\in\Delta\mathcal{S}
$$

such that:

$$
\alpha:\mathcal{E}\rightarrow\Delta\mathcal{S}
$$

**Proof sketch:**

By the Effect Generation Principle:

$$
\alpha:
\mathcal{E}
\rightarrow
\Delta\mathcal{S}
$$

is defined as a function.

A function assigns exactly one output to each input.

Therefore:

$$
\exists!\alpha(e)
$$

holds.

**Conclusion:**

The Effect is the unique state change associated with an Event.

---

## State Transition Determinacy Theorem

**Statement:**

A deterministic ASM transition produces one next State from a current
State and an Event.

**Assumptions:**

Let:

$$
S_t\in\mathcal{S}
$$

and:

$$
e\in\mathcal{E}
$$

**Formal expression:**

$$
\forall S_t\in\mathcal{S},
\forall e\in\mathcal{E},
\exists!S_{t+1}\in\mathcal{S}
$$

such that:

$$
S_{t+1}
=
\delta(S_t,e)
$$

**Proof sketch:**

The transition function:

$$
\delta:\mathcal{S}\times\mathcal{E}\rightarrow\mathcal{S}
$$

maps each pair:

$$
(S_t,e)
$$

to one State.

Therefore the next State is uniquely determined.

**Conclusion:**

The ASM State Transition is deterministic when $\delta$ is deterministic.

---

## History Reconstruction Theorem

**Statement:**

A State generated from a complete History can be reconstructed by applying
all Effects in sequence.

**Assumptions:**

Let:

$$
H(t)=((e_1,t_1),(e_2,t_2),\dots,(e_n,t_n))
$$

and:

$$
S_0\in\mathcal{S}
$$

**Formal expression:**

$$
\forall H(t)\in\mathcal{H},
\exists G
$$

such that:

$$
S_t=G(H(t))
$$

and:

$$
S_t
=
\delta(
\dots
\delta(
\delta(S_0,e_1),
e_2
)
\dots,
e_n
)
$$

**Proof sketch:**

By repeated application of the State Transition Function:

$$
S_{i+1}=\delta(S_i,e_i)
$$

the final State is obtained by applying every Event in chronological
order.

**Conclusion:**

History contains sufficient information to derive the resulting State.

---

## State Preservation Theorem

**Statement:**

A valid transition preserves all constraints defined on the State.

**Assumptions:**

Let:

$$
C:\mathcal{S}\rightarrow\mathbb{R}
$$

be a Constraint Function.

Assume:

$$
C(S_t)=0
$$

and:

$$
Valid(e)
$$

**Formal expression:**

$$
\forall S_t\in\mathcal{S},
\forall e\in\mathcal{E}
$$

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

**Proof sketch:**

This follows directly from the Constraint Preservation Principle.

**Conclusion:**

Constraints are invariants of valid transitions.

---

## Multiple Representation Theorem

**Statement:**

One History may produce multiple representations.

**Assumptions:**

Let:

$$
H\in\mathcal{H}
$$

and:

$$
Q_1,Q_2\in\mathcal{Q}
$$

with:

$$
Q_1\neq Q_2
$$

**Formal expression:**

$$
\forall H\in\mathcal{H},
\exists F_{Q_1},F_{Q_2}
$$

such that:

$$
F_{Q_1}:
\mathcal{H}
\rightarrow
\mathcal{Y}_{Q_1}
$$

and:

$$
F_{Q_2}:
\mathcal{H}
\rightarrow
\mathcal{Y}_{Q_2}
$$

with:

$$
F_{Q_1}(H)
\neq
F_{Q_2}(H)
$$

being possible.

**Proof sketch:**

The Representation Principle defines a separate representation function
for each Task.

Therefore different Tasks may produce different outputs from the same
History.

**Conclusion:**

Representation depends on purpose.

---

## Information Loss Theorem

**Statement:**

A Representation may contain less information than the original
History.

**Assumptions:**

Let:

$$
F_Q:
\mathcal{H}
\rightarrow
\mathcal{Y}_Q
$$

be a Representation Function.

**Formal expression:**

$$
\exists H_1,H_2\in\mathcal{H}
$$

such that:

$$
H_1\neq H_2
$$

and:

$$
F_Q(H_1)=F_Q(H_2)
$$

**Proof sketch:**

A Representation is a transformation from History into a Task-specific
space.

If the target space has fewer dimensions than the source space, multiple
Histories may map to the same Representation.

**Conclusion:**

A Representation is not necessarily a complete copy of History.

---

## State Sufficiency Theorem

**Statement:**

A State is sufficient for a Task if future transitions required by that
Task can be determined from the State.

**Assumptions:**

Let:

$$
Q\in\mathcal{Q}
$$

and:

$$
S_t=G_Q(H(t))
$$

**Formal expression:**

$$
\exists\delta_Q
$$

such that:

$$
S_{t+1}
=
\delta_Q(S_t,e)
$$

**Proof sketch:**

A Task-dependent State preserves information necessary for the Task.

Information not required by the Task may be removed.

**Conclusion:**

State is not complete History.

State is the minimum information required for future processing.

---

## Theorem Summary

| Theorem | Main Result |
| --- | --- |
| Effect Determinacy Theorem | Events have defined Effects |
| State Transition Determinacy Theorem | Transitions produce next States |
| History Reconstruction Theorem | History generates State |
| State Preservation Theorem | Valid transitions preserve Constraints |
| Multiple Representation Theorem | One History produces multiple Views |
| Information Loss Theorem | Representations may compress History |
| State Sufficiency Theorem | State preserves required information |
