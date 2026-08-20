# ASM Financial Representation v1.2

## Purpose

This document defines the concept of Financial Representation in the
Accounting Layer of the Accounting State Model (ASM).

The purpose is to explain financial statements and other accounting
outputs as purpose-dependent projections of Accounting information.

ASM does not treat financial statements as the Accounting State itself.

---

## Relationship with Accounting Model

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

Financial Representation is generated from these accounting objects.

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

Financial Representation is a projection of Accounting information for a
specific purpose.

---

## Financial Representation Definition

**Financial Representation:**

A Financial Representation is a purpose-dependent transformation that
projects Accounting information into a representation space.

The general form is:

$$
F_Q:
X_Q
\rightarrow
\mathcal{Y}_Q
$$

where:

- $Q$ represents a purpose or Task.
- $X_Q$ represents the required Accounting Information Space.
- $\mathcal{Y}_Q$ represents the Representation Space.

The required input depends on the purpose.

---

## Representation as Projection

A Representation does not create accounting meaning.

It extracts required information from the underlying model.

Therefore:

$$
Representation
=
Projection(Accounting\ Information)
$$

Different purposes may select different projections.

---

## Purpose-Dependent Representation

For:

$$
Q_1,Q_2\in\mathcal{Q}
$$

there exist:

$$
F_{Q_1}:X_{Q_1}\rightarrow\mathcal{Y}_{Q_1}
$$

and:

$$
F_{Q_2}:X_{Q_2}\rightarrow\mathcal{Y}_{Q_2}
$$

such that:

$$
F_{Q_1}(X)
\neq
F_{Q_2}(X)
$$

may hold.

Therefore:

$$
One\ Accounting\ Model
\rightarrow
Multiple\ Representations
$$

---

## Balance Sheet Representation

A Balance Sheet represents Accounting Position.

The representation function is:

$$
BS:
\mathcal{S}_{acc}
\rightarrow
\mathcal{Y}_{BS}
$$

The input is:

$$
S_{acc,t}
=
(A_t,L_t,E_t)
$$

under:

$$
A_t-L_t-E_t=0
$$

Therefore:

$$
Balance\ Sheet
\neq
Accounting\ State
$$

It is a projection of Accounting State.

---

## Income Statement Representation

An Income Statement represents accumulated Performance Flow.

For:

$$
I=[t_0,t_1]
$$

Performance Flow is:

$$
\Pi(I)
=
\sum_{e\in H_I}
\alpha_{\Pi}(e)
$$

The representation is:

$$
IS_I:
\Pi(I)
\rightarrow
\mathcal{Y}_{IS}
$$

The Income Statement does not represent a point-in-time State.

It represents accumulated Effects during a period.

---

## Cash Flow Representation

A Cash Flow Statement represents accumulated cash-related Effects.

For:

$$
I=[t_0,t_1]
$$

Cash Flow is:

$$
\Phi_C(I)
=
\sum_{e\in H_I}
\alpha_C(e)
$$

The representation is:

$$
CF_I:
\Phi_C(I)
\rightarrow
\mathcal{Y}_{CF}
$$

---

## Relationship with Double Entry

Double Entry is also a Representation.

However, it represents Accounting Effects.

The relationship is:

$$
Accounting\ Effect
\rightarrow
Journal\ Representation
$$

Financial Statements represent different accounting objects:

$$
State
\rightarrow
Balance\ Sheet
$$

$$
Performance\ Flow
\rightarrow
Income\ Statement
$$

$$
Cash\ Flow
\rightarrow
Cash\ Flow\ Statement
$$

---

## Representation and Information Loss

Representations may omit information not required for their purpose.

There may exist:

$$
X_1\neq X_2
$$

but:

$$
F_Q(X_1)=F_Q(X_2)
$$

Therefore:

Representation is an abstraction.

---

## Summary

Financial Representation is a purpose-dependent projection of Accounting
information.

The structure is:

$$
Accounting\ Information
\rightarrow
Financial\ Representation
$$

Examples:

$$
State
\rightarrow
Balance\ Sheet
$$

$$
Performance\ Flow
\rightarrow
Income\ Statement
$$

$$
Cash\ Flow
\rightarrow
Cash\ Flow\ Statement
$$

ASM separates:

- Economic Reality
- Accounting Event
- Accounting Effect
- Accounting State
- Financial Representation

Therefore:

$$
\boxed{
Financial\ Statements\ are\ projections\ of\ Accounting\ information,\ not\ the\ Accounting\ State\ itself
}
$$
