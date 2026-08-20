# ASM Accounting State v1.0

## Purpose

This document defines the Accounting State Space introduced by the
Accounting Layer of ASM.

The Accounting Layer specializes the Formal Core State Space for
accounting purposes.

---

## Accounting State Space

**Definition:**

The Accounting State Space represents all possible accounting conditions
of an economic entity.

**Symbol:**

$$
\mathcal{S}_{acc}
$$

The relationship with the Formal Core State Space is:

$$
\iota_{acc}:
\mathcal{S}_{acc}
\rightarrow
\mathcal{S}
$$

---

## Accounting State

**Definition:**

An Accounting State is a state representation containing information
required to describe the accounting condition at time $t$.

**Symbol:**

$$
S_{acc,t}
$$

**Formal expression:**

$$
S_{acc,t}\in\mathcal{S}_{acc}
$$

---

## Accounting State Components

An Accounting State is represented as:

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

where:

- $A_t$ represents Asset position.
- $L_t$ represents Liability position.
- $E_t$ represents Equity position.
- $\Pi_t$ represents accumulated Performance.
- $\Phi_{C,t}$ represents accumulated Cash Flow.

---

## State Transition

An Accounting Event produces an Accounting Effect:

$$
\alpha_{acc}:
\mathcal{E}_{acc}
\rightarrow
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
