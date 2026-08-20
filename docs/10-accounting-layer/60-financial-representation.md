# ASM Financial Representation v1.1

## Purpose

This document defines the concept of Financial Representation in the
Accounting Layer of the Accounting State Model (ASM).

The purpose is to explain financial statements and other accounting
outputs as representations generated from Accounting information.

ASM does not treat financial statements as the Accounting State itself.

---

## Relationship with Accounting State

The Accounting Layer defines:

$$
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Accounting\ History
\rightarrow
Accounting\ State
$$

Financial Representation is generated from these underlying accounting
objects.

The general relationship is:

$$
Accounting\ Information
\rightarrow
Financial\ Representation
$$

Therefore:

$$
Financial\ Representation
\neq
Accounting\ State
$$

Financial Representation is a purpose-dependent projection of Accounting
information.

---

## Financial Representation Definition

**Financial Representation:**

A Financial Representation is a transformation of Accounting information
into a form suitable for a specific purpose.

The general Representation Function is:

$$
F_Q:
(\mathcal{H}_{acc},\mathcal{S}_{acc})
\rightarrow
\mathcal{Y}_Q
$$

where:

- $\mathcal{H}_{acc}$ represents Accounting History.
- $\mathcal{S}_{acc}$ represents Accounting State.
- $Q$ represents a Task or purpose.
- $\mathcal{Y}_Q$ represents the resulting Representation Space.

The required input depends on the purpose of the Representation.

---

## Purpose-Dependent Representation

A single Accounting History and State may produce multiple
representations.

For:

$$
Q_1,Q_2\in\mathcal{Q}
$$

there exist:

$$
F_{Q_1}
:
(\mathcal{H}_{acc},\mathcal{S}_{acc})
\rightarrow
\mathcal{Y}_{Q_1}
$$

and:

$$
F_{Q_2}
:
(\mathcal{H}_{acc},\mathcal{S}_{acc})
\rightarrow
\mathcal{Y}_{Q_2}
$$

such that:

$$
F_{Q_1}(H,S)
\neq
F_{Q_2}(H,S)
$$

may hold.

Therefore:

$$
One\ Accounting\ Model
\rightarrow
Multiple\ Representations
$$

---

## Financial Statements as Representations

Financial statements are examples of Financial Representations.

Examples include:

- Balance Sheet
- Income Statement
- Cash Flow Statement

Each statement represents a different aspect of Accounting information.

They are not independent sources of accounting meaning.

They are generated from the same underlying Accounting Model.

---

## Balance Sheet Representation

A Balance Sheet represents a view of Accounting State focused on
financial position.

Formally:

$$
BS:
\mathcal{S}_{acc}
\rightarrow
\mathcal{Y}_{BS}
$$

The Balance Sheet represents the position dimensions of Accounting State:

$$
S_{acc,t}
=
(A_t,L_t,E_t)
$$

under the Accounting Constraint:

$$
A_t-L_t-E_t=0
$$

Therefore:

$$
Balance\ Sheet
\neq
Accounting\ State
$$

The Balance Sheet is a representation of Accounting State.

---

## Income Statement Representation

An Income Statement represents accumulated performance changes over a
period.

The underlying concept is:

$$
Performance\ Flow
$$

For a period:

$$
I=[t_0,t_1]
$$

the representation is:

$$
IS_I:
\mathcal{H}_{acc}(I)
\rightarrow
\mathcal{Y}_{IS}
$$

The Income Statement does not represent a point-in-time State.

It represents accumulated Accounting Effects related to performance.

Therefore:

$$
Income\ Statement
\neq
Accounting\ State
$$

---

## Cash Flow Representation

A Cash Flow Statement represents accumulated changes in cash-related
dimensions during a period.

For a period:

$$
I=[t_0,t_1]
$$

the representation is:

$$
CF_I:
\mathcal{H}_{acc}(I)
\rightarrow
\mathcal{Y}_{CF}
$$

The Cash Flow Statement is a period-based representation.

It represents accumulated cash-related Effects.

---

## State and Representation Separation

ASM separates:

**State:**

The underlying accounting condition.

$$
S_{acc,t}
$$

**Representation:**

A purpose-dependent view generated from Accounting information.

$$
F_Q(H_{acc},S_{acc})
$$

Therefore:

$$
State
\neq
View
$$

Different users may require different representations of the same
Accounting Model.

---

## Representation and Information Loss

A representation does not necessarily preserve all information.

There may exist:

$$
H_1,H_2\in\mathcal{H}_{acc}
$$

such that:

$$
H_1\neq H_2
$$

but:

$$
F_Q(H_1,S)
=
F_Q(H_2,S)
$$

Therefore:

Financial representations are abstractions.

They preserve information required for a purpose while omitting other
information.

---

## Relationship with Double Entry

Double Entry is also a representation.

The relationship is:

$$
Accounting\ Effect
\rightarrow
Journal\ Representation
$$

Financial Statements are other representations:

$$
Accounting\ State
+
Accounting\ History
\rightarrow
Financial\ Representation
$$

Both originate from accounting information but serve different purposes.

---

## Future Extension

Future documents may introduce:

- financial reporting structures
- management accounting views
- ERP reporting dimensions
- analytical representations

These are extensions of the Representation Layer.

---

## Summary

Financial Representation is a purpose-dependent projection generated from
Accounting information.

The fundamental structure is:

$$
Accounting\ History
\rightarrow
Accounting\ State
\rightarrow
Financial\ Representation
$$

Different representations focus on different aspects:

$$
State
\rightarrow
Balance\ Sheet
$$

$$
Effect\ Aggregation
\rightarrow
Income\ Statement
$$

$$
Cash\ Effect\ Aggregation
\rightarrow
Cash\ Flow\ Statement
$$

ASM separates:

- accounting reality
- accounting event
- accounting effect
- accounting state
- accounting representation

Therefore:

$$
\boxed{
Financial\ Statements\ are\ projections\ of\ Accounting\ information,\ not\ the\ Accounting\ State\ itself
}
$$
