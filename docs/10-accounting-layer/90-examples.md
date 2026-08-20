# ASM Accounting Examples v1.1

## Purpose

This document provides examples of the Accounting Layer of the
Accounting State Model (ASM).

The purpose is to demonstrate how accounting concepts are represented
through the ASM structure.

ASM separates:

- economic occurrence
- accounting recognition
- state change
- representation

The information flow is:

$$
Economic\ Reality
\rightarrow
Accounting\ Event
\rightarrow
Accounting\ History
\rightarrow
Accounting\ State
\rightarrow
Representation
$$

The state transition mechanism is:

$$
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Accounting\ State
$$

---

## Example 1: Cash Purchase of Equipment

**Economic Reality:**

An entity purchases equipment and pays cash.

The economic occurrence is:

$$
Economic\ Event
$$

representing:

"An economic resource is acquired and cash is transferred."

---

**Accounting Event:**

The accounting model recognizes this occurrence.

$$
e_{acc}\in\mathcal{E}_{acc}
$$

The Accounting Event represents:

"An asset exchange within the entity."

---

**Accounting Effect:**

The Accounting Event generates an Accounting Effect:

$$
\alpha_{acc}(e_{acc})
$$

The change occurs inside Asset dimensions.

For example:

$$
Equipment:+x
$$

and:

$$
Cash:-x
$$

Therefore:

$$
\Delta A=0
$$

because the total Asset amount does not change.

The Accounting Effect preserves:

$$
A-L-E=0
$$

---

**Journal Representation:**

The Accounting Effect is represented through Double Entry:

$$
Accounting\ Effect
\rightarrow
Journal\ Representation
$$

The Journal Entry describes the Effect.

It does not create the Accounting Event or the Accounting Effect.

---

**State Transition:**

The Accounting State changes through:

$$
S_{acc,t+1}
=
\delta_{acc}
(
S_{acc,t},
\alpha_{acc}(e_{acc})
)
$$

The resulting state reflects:

- increased equipment
- decreased cash

while maintaining the Accounting Constraint.

---

## Example 2: Credit Sale

**Economic Reality:**

An entity provides goods or services and receives payment later.

The economic occurrence is:

$$
Economic\ Event
$$

representing:

"An exchange occurs with future payment."

---

**Accounting Event:**

The accounting model recognizes:

$$
e_{acc}\in\mathcal{E}_{acc}
$$

representing:

"Revenue recognition with creation of a receivable."

---

**Accounting Effect:**

The Effect changes Accounting State and Performance Flow.

Position change:

$$
\Delta A>0
$$

because a receivable is created.

Performance change:

$$
\Delta\Pi>0
$$

because performance is recognized.

Therefore:

$$
State\ Change
\neq
Performance\ Flow
$$

The receivable affects Accounting State.

The performance effect is accumulated as a period flow.

---

**State Transition:**

The state update is:

$$
S_{acc,t+1}
=
\delta_{acc}
(
S_{acc,t},
\alpha_{acc}(e_{acc})
)
$$

The Accounting State now contains:

- increased receivable
- changed equity position through accumulated performance

---

## Representation

Different representations are generated from the same Accounting Model.

Balance representation:

$$
BS(S_{acc,t})
\rightarrow
\mathcal{Y}_{BS}
$$

Performance representation:

$$
IS(H_{acc}(I))
\rightarrow
\mathcal{Y}_{IS}
$$

The same Accounting History produces different views.

---

## Example 3: Expense Recognition

**Economic Reality:**

An entity consumes resources during operations.

---

**Accounting Event:**

The accounting model recognizes:

$$
e_{acc}
$$

representing:

"Resource consumption affecting performance."

---

**Accounting Effect:**

The Effect includes:

$$
\Delta\Pi<0
$$

because performance decreases.

The corresponding State change preserves:

$$
A-L-E=0
$$

---

**Interpretation:**

The important point is:

The expense is not identical to the original economic occurrence.

It is an Accounting Event generated through recognition rules.

Therefore:

$$
Economic\ Consumption
\neq
Accounting\ Expense
$$

---

## Example 4: Period Representation

Consider Accounting History during:

$$
I=[t_0,t_1]
$$

The accumulated Effects are:

$$
\sum_{e\in H_I}
\alpha_{acc}(e)
$$

Different representations are generated.

---

## Balance Representation

The Balance Sheet represents position at time $t$.

$$
BS:
\mathcal{S}_{acc}
\rightarrow
\mathcal{Y}_{BS}
$$

It represents:

$$
S_{acc,t}
=
(A_t,L_t,E_t)
$$

under:

$$
A_t-L_t-E_t=0
$$

---

## Performance Representation

The Income Statement represents accumulated Performance Flow.

$$
IS_I:
H_{acc}(I)
\rightarrow
\mathcal{Y}_{IS}
$$

It represents:

$$
\Pi(I)
$$

The Income Statement is not a State.

It is an accumulated Flow representation.

---

## Cash Representation

The Cash Flow Statement represents accumulated cash-related Effects.

$$
CF_I:
H_{acc}(I)
\rightarrow
\mathcal{Y}_{CF}
$$

It represents:

$$
\Phi_C(I)
$$

The Cash Flow Statement is a period representation.

---

## Example 5: Same Accounting Model, Multiple Views

Given:

$$
H_{acc}(t)
$$

and:

$$
S_{acc,t}
$$

the following representations may exist:

$$
BS(S_{acc,t})
$$

$$
IS(H_{acc}(I))
$$

$$
CF(H_{acc}(I))
$$

These are different projections of the same Accounting Model.

Therefore:

$$
Representation
\neq
Reality
$$

and:

$$
Representation
\neq
State
$$

---

## Example 6: Reconstruction from History

Given Accounting History:

$$
H_{acc}(t)
=
((e_1,t_1),(e_2,t_2),...,(e_n,t_n))
$$

the Accounting State can be reconstructed:

$$
S_{acc,t}
=
G_{acc}(H_{acc}(t))
$$

The same State can be reproduced if:

- History is preserved.
- Transition rules are preserved.

This is the accounting application of Event Sourcing.

---

## Summary

ASM represents accounting through:

$$
Economic\ Reality
\rightarrow
Accounting\ Event
\rightarrow
Accounting\ History
\rightarrow
Accounting\ State
\rightarrow
Representation
$$

The state transition mechanism is:

$$
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Accounting\ State
$$

The key distinctions are:

**Event:**

What occurred.

**Effect:**

What changed.

**State:**

The resulting accounting condition.

**Flow:**

Accumulated Effects over a period.

**Representation:**

How accounting information is viewed.

Therefore:

$$
\boxed{
Accounting\ is\ a\ constrained\ event-driven\ state\ transition\ system
}
$$
