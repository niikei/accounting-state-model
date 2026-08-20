# ASM Financial Statement v1.0

## Purpose

This document defines Financial Statements as task-dependent
representations of Accounting History in ASM.

Financial Statements are not independent accounting objects.

They are representations generated from accumulated Accounting History.

---

## Accounting History

Accounting Events are accumulated as Accounting History.

**Symbol:**

$$
H_{acc,t}
$$

**Formal expression:**

$$
H_{acc,t}
\in
(\mathcal{E}_{acc}\times T)^*
$$

Accounting History contains ordered Accounting Events and their timestamps.

---

## Financial Representation Function

A Financial Statement is a representation generated from Accounting
History.

The representation function is:

$$
F_Q:
\mathcal{H}_{acc}
\rightarrow
\mathcal{Y}_Q
$$

where:

- $Q$ represents the purpose of the representation.
- $\mathcal{Y}_Q$ represents the output space required by that purpose.

---

## Balance Sheet Representation

The Balance Sheet represents the financial position at a specific time.

The Balance Sheet representation function is:

$$
F_{BS}
:
\mathcal{H}_{acc}
\rightarrow
\mathcal{Y}_{BS}
$$

The resulting representation is:

$$
BS_t
=
F_{BS}(H_{acc,t})
$$

The Balance Sheet contains:

$$
(A_t,L_t,E_t)
$$

and satisfies:

$$
A_t-L_t-E_t=0
$$

---

## Income Statement Representation

The Income Statement represents accumulated performance over a period.

The Income Statement representation function is:

$$
F_{PL}
:
\mathcal{H}_{acc}
\rightarrow
\mathcal{Y}_{PL}
$$

For a period:

$$
\tau=[t_0,t_1]
$$

the performance representation is:

$$
PL_{\tau}
=
F_{PL}(H_{acc,\tau})
$$

The accumulated performance is:

$$
\Pi(\tau)
=
\sum_{e\in H_{acc,\tau}}
\alpha_{\Pi}(e)
$$

---

## Cash Flow Representation

The Cash Flow Statement represents changes in cash position.

The Cash Flow representation function is:

$$
F_{CF}
:
\mathcal{H}_{acc}
\rightarrow
\mathcal{Y}_{CF}
$$

For a period:

$$
\tau=[t_0,t_1]
$$

the cash flow representation is:

$$
CF_{\tau}
=
F_{CF}(H_{acc,\tau})
$$

The accumulated cash effect is:

$$
\Phi_C(\tau)
=
\sum_{e\in H_{acc,\tau}}
\alpha_C(e)
$$

---

## Multiple Views of the Same History

A single Accounting History may generate multiple Financial Statements.

Formally:

$$
H_{acc,t}\in\mathcal{H}_{acc}
$$

and:

$$
F_{BS}(H_{acc,t})
$$

$$
F_{PL}(H_{acc,t})
$$

$$
F_{CF}(H_{acc,t})
$$

are different representations of the same underlying History.

Therefore:

$$
Financial\ Statement
\neq
Accounting\ History
$$

---

## Reconstruction Principle

A Financial Statement can be reconstructed from Accounting History if:

1. Accounting Events are preserved.
2. Accounting Effects are defined.
3. Representation Functions are defined.

Formally:

$$
H_{acc,t}
\rightarrow
S_{acc,t}
\rightarrow
F_Q(H_{acc,t})
$$

---

## Interpretation

ASM changes the perspective of Financial Statements.

Traditional view:

$$
Journal
\rightarrow
Financial\ Statement
$$

ASM view:

$$
Accounting\ History
\rightarrow
State
\rightarrow
Purpose\ dependent\ Representation
$$

Financial Statements are therefore projections of Accounting State and
History.

---

## Consequence

Different users may require different representations of the same
Accounting History.

Examples:

- Investors require financial position.
- Managers require operational performance.
- Tax authorities require regulatory views.

The underlying Accounting History remains the same.

Only the Representation Function changes.

---

## Summary

The ASM interpretation of Financial Statements is:

$$
\boxed{
Financial\ Statement
=
Projection(Accounting\ History)
}
$$

The Accounting History is the source.

The Financial Statement is a view.
