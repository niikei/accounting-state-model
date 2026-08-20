# ASM Accounting Constraint v1.0

## Purpose

This document defines the fundamental constraints applied to the
Accounting State Space in ASM.

The constraints represent invariant properties that must be preserved
during Accounting State transitions.

---

## Accounting Constraint Function

**Definition:**

An Accounting Constraint Function defines validity conditions for an
Accounting State.

**Symbol:**

$$
\kappa_{acc}
$$

**Formal expression:**

$$
\kappa_{acc}:
\mathcal{S}_{acc}
\rightarrow
\mathbb{R}
$$

A valid Accounting State satisfies:

$$
\kappa_{acc}(S_{acc,t})=0
$$

---

## Accounting Identity Constraint

**Statement:**

The fundamental accounting identity is an invariant of the Accounting
State.

The Accounting State is:

$$
S_{acc,t}
=
(
A_t,
L_t,
E_t,
\Pi_t,
\Phi_{C,t}
)
$$

The accounting identity is:

$$
A_t-L_t-E_t=0
$$

---

## Accounting Constraint Definition

The Accounting Constraint Function is defined as:

$$
\kappa_{acc}(S_{acc,t})
=
A_t-L_t-E_t
$$

Therefore:

$$
\kappa_{acc}(S_{acc,t})=0
$$

is equivalent to:

$$
A_t=L_t+E_t
$$

---

## Constraint Preservation

An Accounting Event generates an Accounting Effect:

$$
\alpha_{acc}(e_{acc})
\in
\Delta\mathcal{S}_{acc}
$$

The Accounting State transition is:

$$
S_{acc,t+1}
=
\delta_{acc}
(
S_{acc,t},
\alpha_{acc}(e_{acc})
)
$$

A valid transition must preserve:

$$
\kappa_{acc}(S_{acc,t+1})=0
$$

---

## Interpretation

The accounting identity is not an additional calculation rule.

It is an invariant condition defining valid Accounting States.

Therefore:

$$
\boxed{
A=L+E
}
$$

is a property of the Accounting State Space.

---

## Consequence

Every valid Accounting Effect must transform one valid Accounting State
into another valid Accounting State.

Formally:

If:

$$
\kappa_{acc}(S_{acc,t})=0
$$

and:

$$
Valid(e_{acc})
$$

then:

$$
\kappa_{acc}
(
\delta_{acc}
(
S_{acc,t},
\alpha_{acc}(e_{acc})
)
)
=0
$$
