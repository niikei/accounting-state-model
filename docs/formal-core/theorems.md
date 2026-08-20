# ASM Theorems v2.0

## Purpose

This document defines the mathematical properties derived from the axioms
and definitions of the Accounting State Model (ASM).

A theorem is a property that follows from the formal structure of ASM.

---

## Double Entry Conservation Theorem

**Statement:**

Every valid Accounting Event transition preserves the Double Entry
Constraint.

**Assumptions:**

Let:

$$
e\in\mathcal{E}_{acc}
$$

and:

$$
t\in T
$$

Assume:

$$
Valid(e)
$$

and:

$$
\mathsf{Bal}_B(B_t)=0
$$

**Formal expression:**

$$
\forall e\in\mathcal{E}_{acc},
\forall t\in T
$$

$$
Valid(e)
\land
\mathsf{Bal}_B(B_t)=0
\Rightarrow
\mathsf{Bal}_B(B_{t+1})=0
$$

**Proof sketch:**

By the Valid Transition Preservation Principle,

$$
Valid(e)
\land
C(S_t)=0
\Rightarrow
C(S_{t+1})=0
$$

Taking:

$$
C=\mathsf{Bal}_B
$$

gives:

$$
\mathsf{Bal}_B(B_{t+1})=0
$$

**Conclusion:**

Double-entry balance is an invariant preserved by valid accounting
transitions.

---

## Financial Position Identity Theorem

**Statement:**

Every valid Financial Position satisfies the accounting identity.

**Assumptions:**

Let:

$$
FP_t=(A_t,L_t,E_t)
$$

be a valid Financial Position.

**Formal expression:**

$$
\forall t\in T
$$

$$
FP_t=(A_t,L_t,E_t)
\Rightarrow
A_t-L_t-E_t=0
$$

**Proof sketch:**

Financial Position is generated from accumulated Accounting Effects.

The Accounting Dimension Space preserves the accounting constraint.

Therefore:

$$
A_t-L_t-E_t=0
$$

is an invariant.

**Conclusion:**

The balance sheet equation is a preserved structural property, not an
independent calculation rule.

---

## Effect Accumulation Theorem

**Statement:**

Every Position is the accumulation of Accounting Effects over History.

**Assumptions:**

Let:

$$
k\in\{A,L,E,C\}
$$

be an accounting dimension.

Let:

$$
H_A(t)
$$

be Accounting Event History.

**Formal expression:**

$$
\forall k\in\{A,L,E,C\}
$$

$$
P_k(t)
=
P_k(0)
+
\sum_{e\in H_A(t)}
\alpha_k(e)
$$

**Proof sketch:**

From the definition of Quantitative Position:

$$
P_k(t)
=
P_k(0)
+
\sum_e\alpha_k(e)
$$

Therefore every position is the integral accumulation of historical
effects.

**Conclusion:**

A current accounting position contains accumulated consequences of past
Accounting Events.

---

## Multiple Representation Theorem

**Statement:**

A single Accounting History can generate multiple Task-dependent
representations.

**Assumptions:**

Let:

$$
H_A\in\mathcal{H}_{acc}
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
\forall H_A\in\mathcal{H}_{acc},
\forall Q\in\mathcal{Q},
\exists F_Q
$$

such that:

$$
F_Q:
\mathcal{H}_{acc}
\rightarrow
Y_Q
$$

**Proof sketch:**

From the Representation Principle:

$$
\forall Q\in\mathcal{Q},
\exists F_Q
$$

Therefore different Tasks may define different representation mappings.

**Conclusion:**

Financial statements, management reports, and ERP operational states
are different projections of the same Accounting History.

---

## State Sufficiency Theorem

**Statement:**

A State is sufficient for a Task if future Task-relevant transitions are
uniquely determined from that State.

**Assumptions:**

Let:

$$
S_t=G_Q(H_A(t))
$$

for:

$$
Q\in\mathcal{Q}
$$

**Formal expression:**

$$
\forall e\in\mathcal{E}_{acc},
\exists!
S_{t+1}
$$

such that:

$$
S_{t+1}
=
\delta_Q(S_t,e)
$$

**Proof sketch:**

Operational State is defined as a Task-dependent compression:

$$
S_t=G_Q(H_A(t))
$$

If:

$$
\delta_Q
$$

is deterministic, the next state is uniquely determined.

**Conclusion:**

A State does not need to contain all History.

It must contain all information required for the Task.

---

## Flow-Stock Relationship Theorem

**Statement:**

A Stock change equals the accumulated Flow effect over a period.

**Assumptions:**

Let:

$$
I=[t_0,t_1]\subseteq T
$$

and:

$$
k\in\{A,L,E,C\}
$$

**Formal expression:**

$$
\forall k\in\{A,L,E,C\}
$$

$$
P_k(t_1)-P_k(t_0)
=
\sum_{e\in H_I}
\alpha_k(e)
$$

**Proof sketch:**

From Position definition:

$$
P_k(t)
=
P_k(0)
+
\sum_e\alpha_k(e)
$$

Subtracting two time points gives:

$$
\Delta P_k
=
\sum_{e\in H_I}
\alpha_k(e)
$$

**Conclusion:**

Flow represents accumulated change.

Stock represents the resulting accumulated position.

---

## Performance-Cash Separation Theorem

**Statement:**

Performance Flow and Cash Flow are different projections of Accounting
Effects.

**Assumptions:**

Let:

$$
\alpha(e)
=
(\Delta A,\Delta L,\Delta E,\Delta\Pi,\Delta\Phi_C)
$$

**Formal expression:**

$$
\Pi(I)
=
\sum_{e\in H_I}
\alpha_\Pi(e)
$$

and:

$$
\Phi_C(I)
=
\sum_{e\in H_I}
\alpha_C(e)
$$

There exists an Accounting Event:

$$
\exists e\in\mathcal{E}_{acc}
$$

such that:

$$
\alpha_\Pi(e)\neq0
$$

and:

$$
\alpha_C(e)=0
$$

**Proof sketch:**

A credit sale produces performance recognition without immediate cash
movement.

Therefore:

$$
\Pi(I)\neq\Phi_C(I)
$$

in general.

**Conclusion:**

Profit and Cash Flow are different projections of the same Accounting
History.

---

## Event Effect Conservation Theorem

**Statement:**

Every Accounting Event affects Accounting Dimensions through an Effect
Vector.

**Formal expression:**

$$
\forall e\in\mathcal{E}_{acc},
\exists!
\alpha(e)
$$

such that:

$$
\alpha(e)\in\Delta\mathcal{X}
$$

**Proof sketch:**

From the Accounting Effect Definition:

$$
\alpha:
\mathcal{E}_{acc}
\rightarrow
\Delta\mathcal{X}
$$

Therefore each Accounting Event has a corresponding Effect Vector.

**Conclusion:**

The Effect Vector is the fundamental bridge between Events and Accounting
States.

---

## Theorem Summary

| Theorem | Main Result |
| --- | --- |
| Double Entry Conservation Theorem | Double-entry constraints are preserved |
| Financial Position Identity Theorem | $A-L-E=0$ is invariant |
| Effect Accumulation Theorem | Positions accumulate Effects |
| Multiple Representation Theorem | One History produces multiple views |
| State Sufficiency Theorem | State is sufficient Task-dependent memory |
| Flow-Stock Relationship Theorem | Stock is accumulated Flow |
| Performance-Cash Separation Theorem | Profit and Cash are different projections |
| Event Effect Conservation Theorem | Events generate Effect Vectors |
