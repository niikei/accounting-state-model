# ASM Accounting Layer Overview v1.0

## Purpose

This document provides an overview of the Accounting Layer of the
Accounting State Model (ASM).

The Accounting Layer specializes the Formal Core for accounting domains.

The Formal Core defines the general structure of:

$$
Event
\rightarrow
Effect
\rightarrow
State
$$

The Accounting Layer introduces accounting-specific concepts.

---

## Layer Structure

The relationship between the Formal Core and Accounting Layer is:

$$
Formal\ Core
\rightarrow
Accounting\ Layer
$$

The Formal Core defines:

$$
\mathcal{S}
$$

The Accounting Layer defines:

$$
\mathcal{S}_{acc}
$$

with:

$$
\iota_{acc}
:
\mathcal{S}_{acc}
\rightarrow
\mathcal{S}
$$

---

## Accounting Flow

The complete accounting flow is:

$$
Reality
\rightarrow
Evidence
\rightarrow
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Accounting\ State
\rightarrow
Financial\ Representation
$$

Mathematically:

$$
\mathcal{R}
\rightarrow
\mathcal{Z}_{acc}
\rightarrow
\mathcal{E}_{acc}
\rightarrow
\Delta\mathcal{S}_{acc}
\rightarrow
\mathcal{S}_{acc}
\rightarrow
\mathcal{Y}_Q
$$

---

## Accounting Event

An Accounting Event represents an economic occurrence recognized by an
accounting system.

$$
e_{acc}\in\mathcal{E}_{acc}
$$

An Accounting Event is generated from accounting evidence:

$$
R_{acc}
:
\mathcal{Z}_{acc}
\times
\Theta_{acc}
\times
\mathcal{M}_{acc}
\rightarrow
\mathcal{E}_{acc}
$$

---

## Accounting Effect

An Accounting Event generates an Accounting Effect:

$$
\alpha_{acc}
:
\mathcal{E}_{acc}
\rightarrow
\Delta\mathcal{S}_{acc}
$$

The Accounting Effect represents the change caused by the event.

$$
\alpha_{acc}(e_{acc})
\in
\Delta\mathcal{S}_{acc}
$$

---

## Accounting State

The Accounting State represents the accounting condition of an entity.

$$
S_{acc,t}
\in
\mathcal{S}_{acc}
$$

The Accounting State is represented as:

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

- $A_t$ represents Assets.
- $L_t$ represents Liabilities.
- $E_t$ represents Equity.
- $\Pi_t$ represents Performance.
- $\Phi_{C,t}$ represents Cash Flow.

---

## Accounting Constraint

Valid Accounting States satisfy the Accounting Constraint.

The Constraint Function is:

$$
\kappa_{acc}
:
\mathcal{S}_{acc}
\rightarrow
\mathbb{R}
$$

The fundamental invariant is:

$$
\kappa_{acc}(S_{acc,t})
=
A_t-L_t-E_t
$$

Therefore:

$$
\kappa_{acc}(S_{acc,t})=0
$$

---

## Accounting State Transition

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

A valid transition preserves:

$$
\kappa_{acc}(S_{acc,t+1})=0
$$

Therefore:

$$
Valid\ Event
\rightarrow
Valid\ State
$$

---

## Double Entry Representation

Double Entry represents Accounting Effects.

The representation function is:

$$
J:
\Delta\mathcal{S}_{acc}
\rightarrow
\mathcal{J}
$$

where:

$$
j\in\mathcal{J}
$$

is a Journal Entry.

A valid Journal Entry satisfies:

$$
D(j)-C(j)=0
$$

Double Entry is therefore a representation constraint.

It is not the source of accounting meaning.

---

## Financial Representation

Financial Statements are representations generated from Accounting
History.

The representation function is:

$$
F_Q:
\mathcal{H}_{acc}
\rightarrow
\mathcal{Y}_Q
$$

Examples:

Balance Sheet:

$$
BS_t=F_{BS}(H_{acc,t})
$$

Income Statement:

$$
PL_{\tau}=F_{PL}(H_{acc,\tau})
$$

Cash Flow Statement:

$$
CF_{\tau}=F_{CF}(H_{acc,\tau})
$$

---

## Core Accounting Model

The complete ASM Accounting Layer is:

$$
\boxed{
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Accounting\ State
\rightarrow
Financial\ Representation
}
$$

with:

$$
e_{acc}
\rightarrow
\alpha_{acc}(e_{acc})
\rightarrow
S_{acc,t+1}
\rightarrow
F_Q(H_{acc,t})
$$

---

## Conceptual Interpretation

ASM views accounting as a state transition system.

Traditional view:

$$
Transaction
\rightarrow
Journal
\rightarrow
Statement
$$

ASM view:

$$
Reality
\rightarrow
Recognition
\rightarrow
State\ Change
\rightarrow
Representation
$$

The primary object is not the Journal Entry.

The primary object is the Accounting Effect that changes Accounting
State.

---

## Summary

The Accounting Layer introduces:

| Concept | Role |
| --- | --- |
| Accounting Event | Cause of accounting change |
| Accounting Effect | Change in accounting state |
| Accounting State | Current accounting condition |
| Accounting Constraint | Validity condition |
| Double Entry | Effect representation |
| Financial Statement | Purpose-dependent view |

ASM therefore defines accounting as:

$$
\boxed{
A\ constrained\ state\ transition\ system\ over\ economic\ events
}
$$
