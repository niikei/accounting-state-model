# ASM Accounting Structure v1.2

## Purpose

This document defines the structure of Accounting State and related
dimensions in the Accounting Layer of the Accounting State Model (ASM).

The purpose is to define how accounting information is organized as
mathematical spaces.

This document introduces:

- Accounting State dimensions.
- Accounting constraints.
- Flow dimensions.
- The relationship between position and flow.

---

## Relationship with Accounting State

The Accounting State was previously defined as:

$$
S_{acc,t}\in\mathcal{S}_{acc}
$$

This document defines the internal structure of:

$$
\mathcal{S}_{acc}
$$

An Accounting State is not an arbitrary collection of accounting values.

It is a constrained state representing the accounting condition of an
entity at a specific point in time.

---

## Accounting State Space

The Accounting State Space represents accounting conditions at a point in
time.

The valid Accounting State Space is:

$$
\mathcal{S}_{acc}
$$

An Accounting State is:

$$
S_{acc,t}\in\mathcal{S}_{acc}
$$

The internal structure is defined by position dimensions.

---

## Position Dimensions

Position dimensions represent quantities existing at a specific point in
time.

The position space is:

$$
\mathcal{X}_{pos}
=
\mathcal{A}
\times
\mathcal{L}
\times
\mathcal{E}
$$

where:

- $\mathcal{A}$ represents Asset dimension.
- $\mathcal{L}$ represents Liability dimension.
- $\mathcal{E}$ represents Equity dimension.

---

## Asset Dimension

**Asset:**

Assets represent economic resources controlled by the entity.

The Asset component is:

$$
A_t\in\mathcal{A}
$$

---

## Liability Dimension

**Liability:**

Liabilities represent obligations of the entity.

The Liability component is:

$$
L_t\in\mathcal{L}
$$

---

## Equity Dimension

**Equity:**

Equity represents the residual interest in the entity.

The Equity component is:

$$
E_t\in\mathcal{E}
$$

---

## Accounting Equation Constraint

Not every combination of:

$$
(A_t,L_t,E_t)
$$

represents a valid Accounting State.

The fundamental Accounting Constraint is:

$$
A_t-L_t-E_t=0
$$

Therefore, the valid Accounting State Space is:

$$
\mathcal{S}_{acc}
=
\{
(A,L,E)
\mid
A-L-E=0
\}
$$

The Accounting State Space is a constrained subset:

$$
\mathcal{S}_{acc}
\subseteq
\mathcal{A}
\times
\mathcal{L}
\times
\mathcal{E}
$$

---

## Flow Space

Flow represents accumulated changes over a period.

Flow is not a point-in-time State.

Therefore:

$$
State
\neq
Flow
$$

The Accounting Flow Space is:

$$
\mathcal{F}_{acc}
$$

defined as:

$$
\mathcal{F}_{acc}
=
\mathcal{P}
\times
\mathcal{C}
$$

where:

- $\mathcal{P}$ represents Performance Flow.
- $\mathcal{C}$ represents Cash Flow.

---

## Performance Flow Dimension

**Performance Flow:**

Performance Flow represents accumulated effects related to economic
performance during a period.

For:

$$
I=[t_0,t_1]
$$

Performance Flow is:

$$
\Pi(I)\in\mathcal{P}
$$

The accumulated flow is generated from Accounting History:

$$
\Pi(I)
=
\sum_{e\in H_I}
\alpha_{\Pi}(e)
$$

Performance Flow represents changes over an interval.

It does not represent a condition at a single time point.

---

## Cash Flow Dimension

**Cash Flow:**

Cash Flow represents accumulated changes related to cash during a period.

For:

$$
I=[t_0,t_1]
$$

Cash Flow is:

$$
\Phi_C(I)\in\mathcal{C}
$$

The accumulated flow is:

$$
\Phi_C(I)
=
\sum_{e\in H_I}
\alpha_C(e)
$$

Cash Flow represents temporal change.

It is not a State.

---

## Relationship Between State and Flow

Accounting Events generate Effects.

Effects change Accounting State.

The transition is:

$$
S_{acc,t+1}
=
\delta_{acc}
(
S_{acc,t},
\alpha_{acc}(e_{acc})
)
$$

The accumulated changes over a period may be represented as Flow:

$$
Flow(I)
=
\sum_{e\in H_I}
\alpha(e)
$$

Therefore:

$$
Flow
=
Accumulated\ Effects
$$

and:

$$
State
=
Current\ Condition
$$

---

## Performance Flow and Equity

Performance Flow affects future Accounting State.

Conceptually:

$$
E_{t+1}
=
E_t+\Pi(I)
$$

This relationship is introduced formally in higher layers.

At this layer:

- Performance Flow is a period-based change.
- Equity is a position dimension.

Therefore:

$$
Performance
\neq
Equity
$$

---

## Dimension and Representation Separation

Accounting dimensions define the internal mathematical structure.

They do not define presentation formats.

Therefore:

$$
Accounting\ Structure
\neq
Financial\ Representation
$$

Examples:

- Balance Sheet represents position dimensions.
- Income Statement represents performance flow.
- Cash Flow Statement represents cash flow.

These are representations generated from accounting information.

---

## Future Extension

Future documents may introduce:

- account-level dimensions
- journal coordinates
- debit and credit representation
- aggregation structures
- formal relationship between Performance Flow and Equity

These concepts extend Accounting Structure.

---

## Summary

Accounting Structure separates:

**Position:**

$$
\mathcal{S}_{acc}
$$

from:

**Flow:**

$$
\mathcal{F}_{acc}
$$

The Accounting State Space is:

$$
\mathcal{S}_{acc}
=
\{
(A,L,E)
\mid
A-L-E=0
\}
$$

The Flow Space is:

$$
\mathcal{F}_{acc}
=
\mathcal{P}
\times
\mathcal{C}
$$

ASM therefore models accounting as:

$$
\boxed{
A\ constrained\ state\ system\ with\ position\ states\ and\ accumulated\ flows
}
$$
