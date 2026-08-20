# ASM Glossary v1.0

## Purpose

This document defines the official vocabulary of the Accounting State
Model (ASM).

All ASM documents MUST follow the terminology defined here.

A term that is not defined in this glossary MUST NOT be introduced into
the Formal Core without review.

---

## Fundamental Concepts

### Reality

**Symbol**

\[
\mathcal{R}
\]

**Definition**

Reality is the domain in which economic activities and events occur.

It represents the actual world before accounting interpretation.

Examples:

- Sale of goods
- Acquisition of equipment
- Borrowing money
- Production activity

**Notes**

Reality is not directly stored by accounting systems.

\[
\boxed{
Reality \neq Accounting
}
\]

Accounting requires observation and interpretation.

---

### Evidence

**Symbol**

\[
\mathcal{Z}
\]

**Definition**

Evidence is information observed from Reality or Economic Events that
supports accounting interpretation.

Examples:

- Invoice
- Contract
- Bank statement
- Delivery record

**Relation**

Evidence is connected to Reality through an observation relation.

\[
Obs \subseteq \mathcal{Z}\times\mathcal{R}
\]

**Notes**

Evidence is not Reality itself.

\[
\boxed{
Evidence \neq Reality
}
\]

---

## Event Concepts

### Economic Event

**Symbol**

\[
\epsilon \in \mathcal{E}_E
\]

**Definition**

An Economic Event is a meaningful change occurring in Reality.

Examples:

- Delivery of goods
- Contract formation
- Resource consumption

**Role**

Economic Event represents what happened in the economic world.

---

### Accounting Event

**Symbol**

\[
e \in \mathcal{E}_A
\]

**Definition**

An Accounting Event is an event that has been interpreted and recognized
within an accounting system.

**Generation**

\[
\widehat{\mathsf{Acc}}_{\theta}(z,\eta)=e
\]

where:

- \(z\): Evidence
- \(\eta\): Estimate
- \(\theta\): Accounting Policy

**Notes**

Accounting Event is not identical to Economic Event.

\[
\boxed{
Economic\ Event \neq Accounting\ Event
}
\]

---

## Interpretation Concepts

### Accounting Policy

**Symbol**

\[
\theta \in \Theta
\]

**Definition**

Accounting Policy is the rule system used to interpret and measure
economic events.

Examples:

- IFRS policy
- GAAP policy
- Internal accounting rules

---

### Estimate

**Symbol**

\[
\eta
\]

**Definition**

Estimate represents assumptions about uncertain values or future outcomes
used in accounting interpretation.

Examples:

- Useful life of assets
- Expected credit loss
- Provision rates

---

### Accounting Interpretation

**Symbol**

\[
\widehat{\mathsf{Acc}}_{\theta}
\]

**Definition**

Accounting Interpretation is the transformation process that converts
Evidence into Accounting Events using Policy and Estimates.

---

## Historical Concepts

### Accounting Event History

**Symbol**

\[
H_A
\]

**Definition**

Accounting Event History is an ordered sequence of Accounting Events.

\[
H_A=(e_1,e_2,\dots,e_n)
\]

**Notes**

History is not a set.

Order matters.

\[
(e_1,e_2,e_3)
\neq
\{e_1,e_2,e_3\}
\]

---

### Provenance

**Symbol**

\[
Prov
\]

**Definition**

Provenance represents the origin and supporting information of an
Accounting Event.

It answers:

> Why does this Accounting Event exist?

**Notes**

Provenance is different from correctness.

\[
\boxed{
Provenance \neq Validity
}
\]

---

## Representation Concepts

### Representation

**Symbol**

\[
F
\]

**Definition**

Representation is a transformation of information into a form suitable
for a specific purpose.

General form:

\[
F:
\mathcal{U}
\rightarrow
\mathcal{V}
\]

Examples:

- Financial Statements
- Ledger
- Management Reports
- Operational State

---

### Task

**Symbol**

\[
Q
\]

**Definition**

Task is the purpose or required output that determines what information is
sufficient.

Examples:

- Prepare financial statements
- Forecast cash shortage
- Evaluate profitability

Formal form:

\[
Q:
\mathcal{U}
\rightarrow
\mathcal{W}
\]

---

### Sufficiency

**Definition**

A Representation is sufficient for a Task when the Task output can be
derived from that Representation.

\[
\exists R:
Q=R\circ F
\]

---

## State Concepts

### Operational State

**Symbol**

\[
S
\]

**Definition**

Operational State is a task-sufficient representation of history that
allows future state transitions.

\[
S_{t+1}
=

\delta(S_t,e)
\]

**Notes**

State is not merely a balance.

\[
\boxed{
State \neq Position
}
\]

---

### Quantitative Position

**Symbol**

\[
P
\]

**Definition**

Quantitative Position is a numerical projection obtained from accumulated
effects.

\[
P_t
=

P_0+
\sum_e\alpha(e)
\]

Examples:

- Cash balance
- Inventory quantity
- Debt amount

---

### Financial Position

**Symbol**

\[
FP
\]

**Definition**

Financial Position is a representation of recognized financial resources
and obligations.

It consists of:

\[
A,L,E
\]

where:

- \(A\): Assets
- \(L\): Liabilities
- \(E\): Equity

---

## Accounting Representation Concepts

### Book Representation

**Definition**

Book Representation is the accounting record representation used for
double-entry bookkeeping.

---

### Double Entry Constraint

**Definition**

Double Entry Constraint is a structural balance condition applied to Book
Representation.

\[
Debit = Credit
\]

---

### Report Representation

**Definition**

Report Representation is a task-specific presentation generated from
Accounting History.

Examples:

- Balance Sheet
- Income Statement
- Cash Flow Statement

---

## Validity Concepts

### Validity

**Definition**

Validity represents whether an accounting representation is acceptable
under required criteria.

ASM distinguishes three types.

### Structural Validity

Formal consistency.

Example:

\[
Debit = Credit
\]

### Semantic Validity

Consistency with accounting meaning and rules.

### Empirical Validity

Consistency with Reality and Evidence.

---

## Core Relations

The fundamental ASM flow is:

\[
Reality
\rightarrow
Evidence
\rightarrow
Accounting\ Interpretation
\rightarrow
Accounting\ Event
\rightarrow
History
\rightarrow
Representation
\]

From Representation:

\[
Representation
\rightarrow
State
\]

\[
Representation
\rightarrow
Position
\]

\[
Representation
\rightarrow
Book
\]

\[
Representation
\rightarrow
Report
\]
