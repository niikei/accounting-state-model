# ASM Corollaries v1.0

## Purpose

This document defines corollaries derived from the Formal Core of the
Accounting State Model (ASM).

A corollary is an application-level consequence obtained from ASM
definitions and theorems.

Corollaries connect the mathematical structure of ASM with accounting
systems and practices.

---

## Double-entry Bookkeeping Corollary

**Statement:**

Double-entry bookkeeping is a representation of Accounting Effects that
preserves accounting constraints.

**Formal expression:**

For:

$$
e\in\mathcal{E}_{acc}
$$

there exists:

$$
\alpha(e)
=
(\Delta A,\Delta L,\Delta E,\Delta\Pi,\Delta\Phi_C)
$$

such that the Book Representation satisfies:

$$
\mathsf{Bal}_B(B)=0
$$

**Derivation:**

From the Accounting Effect Definition:

$$
\alpha:
\mathcal{E}_{acc}
\rightarrow
\Delta\mathcal{X}
$$

and the Double Entry Constraint:

$$
\mathsf{Bal}_B(B)=0
$$

Accounting entries are a representation of Effect Vectors.

**Conclusion:**

Debit and Credit are not the fundamental objects.

The fundamental object is:

$$
Event
\rightarrow
Effect
$$

Debit and Credit are a representation mechanism.

---

## Balance Sheet Corollary

**Statement:**

The Balance Sheet is a representation of Financial Position.

**Formal expression:**

$$
BS_t
=
F_{BS}(H_A(t))
$$

where:

$$
FP_t=(A_t,L_t,E_t)
$$

and:

$$
A_t-L_t-E_t=0
$$

**Derivation:**

Financial Position is defined as:

$$
FP_t=(A_t,L_t,E_t)
$$

Therefore the Balance Sheet presents a projection of Financial Position.

**Conclusion:**

The Balance Sheet is a state representation, not a list of independent
accounts.

---

## Income Statement Corollary

**Statement:**

The Income Statement is a Performance Flow representation.

**Formal expression:**

$$
PL_I
=
F_{PL}(H_I)
$$

where:

$$
\Pi(I)
=
\sum_{e\in H_I}
\alpha_\Pi(e)
$$

**Derivation:**

Performance Flow is a projection of Accounting Effects.

Therefore:

$$
Profit(I)=\Pi(I)
$$

under the selected accounting policy.

**Conclusion:**

Profit is accumulated performance effect, not cash accumulation.

---

## Cash Flow Statement Corollary

**Statement:**

The Cash Flow Statement is a Cash Effect projection.

**Formal expression:**

$$
CF_I
=
F_{CF}(H_I)
$$

where:

$$
\Phi_C(I)
=
\sum_{e\in H_I}
\alpha_C(e)
$$

**Derivation:**

Cash Flow and Performance Flow are different projections.

$$
\Pi(I)\neq\Phi_C(I)
$$

in general.

**Conclusion:**

A profitable company may have negative cash flow.

A company with positive cash flow may have negative profit.

---

## Accrual Accounting Corollary

**Statement:**

Accrual accounting separates economic performance from cash movement.

**Formal expression:**

There exist Accounting Events:

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

**Example:**

Credit sale:

$$
\Delta AR>0
$$

$$
\Delta\Pi>0
$$

$$
\Delta\Phi_C=0
$$

**Conclusion:**

Accrual accounting is a consequence of separating Effect dimensions.

---

## Cost Accounting Corollary

**Statement:**

Cost is a classification of Accounting Effects according to purpose.

**Formal expression:**

Let:

$$
\mathcal{C}_{cost}
$$

be a cost dimension.

Then:

$$
\alpha_Cost(e)
$$

is a projection of:

$$
\alpha(e)
$$

**Derivation:**

Accounting Effects contain multiple dimensions.

A cost system defines additional Task-dependent projections.

**Conclusion:**

Different costing methods are different representations of the same
underlying Effects.

Examples:

- Traditional cost accounting
- Activity-based costing
- Throughput accounting

---

## ERP State Corollary

**Statement:**

An ERP system stores Task-dependent representations of Accounting
History.

**Formal expression:**

For an ERP Task:

$$
Q_{ERP}\in\mathcal{Q}
$$

there exists:

$$
F_{ERP}
$$

such that:

$$
F_{ERP}(H_A)=Y_{ERP}
$$

**Derivation:**

ERP systems require operational states.

Operational State is defined as:

$$
S_t=G_Q(H_A(t))
$$

**Conclusion:**

ERP tables are not the fundamental accounting object.

They are representations of Accounting History for specific operational
purposes.

---

## SAP Universal Journal Corollary

**Statement:**

SAP Universal Journal can be interpreted as an implementation of
Effect-oriented accounting storage.

**Formal expression:**

A Universal Journal record represents:

$$
(e,\alpha(e),t)
$$

where:

- $e$ is Accounting Event.
- $\alpha(e)$ is Accounting Effect.
- $t$ is time information.

**Derivation:**

ASM defines Accounting History as:

$$
H_A(t)
=
((e_1,t_1),...,(e_n,t_n))
$$

and Effects as:

$$
\alpha(e)
$$

Therefore ERP accounting records can be modeled as event-effect
representations.

**Conclusion:**

SAP is compatible with an event-oriented accounting model.

---

## Corollary Summary

| Corollary | ASM Interpretation |
| --- | --- |
| Double-entry bookkeeping | Effect representation |
| Balance Sheet | Financial Position projection |
| Income Statement | Performance projection |
| Cash Flow Statement | Cash projection |
| Accrual Accounting | Separation of performance and cash |
| Cost Accounting | Task-dependent effect classification |
| ERP State | Operational representation |
| SAP Universal Journal | Event-effect storage |
