# ASM Formal Core Issues and Revision Plan v1.0

## Purpose

This document summarizes the current issues identified in the
Accounting State Model (ASM) Formal Core and defines the direction for
future revisions.

The purpose is not to redesign ASM from scratch, but to stabilize the
mathematical foundation before further expansion or formal verification.

---

# Current Status

ASM currently defines:

- Formal Core
- Accounting Layer
- Examples
- Glossary

The Formal Core models systems as:

$$
Event
\rightarrow
Effect
\rightarrow
State
$$

and preserves information through:

$$
Reality
\rightarrow
Evidence
\rightarrow
Event
\rightarrow
History
\rightarrow
State
\rightarrow
Representation
$$

The core concept is considered valid.

The current problems are mainly:

- mathematical precision
- notation consistency
- layer separation
- extensibility
- future formal verification readiness

---

# Issue 1: State Generation Function Definition

## Current Problem

Current definition:

$$
G:
\mathcal{H}
\rightarrow
\mathcal{S}
$$

with:

$$
S_t=G(H_t)
$$

is mathematically incomplete.

A State cannot be generated only from History.

State reconstruction requires:

- Initial State
- Effect Function
- Transition Function

because:

$$
S_{t+1}
=
\delta(S_t,\alpha(e))
$$

depends on transition rules.

---

## Example

Same History:

$$
H=((e_1,t_1))
$$

can generate different States.

Initial State:

$$
S_0=0
$$

gives:

$$
S_1=1
$$

Initial State:

$$
S_0=100
$$

gives:

$$
S_1=101
$$

Therefore:

$$
H\rightarrow S
$$

is insufficient.

---

## Required Revision

Replace:

$$
G:
\mathcal{H}
\rightarrow
\mathcal{S}
$$

with:

$$
G_{S_0,\alpha,\delta}
:
\mathcal{H}
\rightarrow
\mathcal{S}
$$

Meaning:

"State Generation Function under fixed initial State,
Effect Function, and Transition Function."

---

# Issue 2: History Content Definition

## Current Problem

History is:

$$
H_t\in(\mathcal{E}\times T)^*
$$

This is conceptually correct.

However, it is unclear whether History stores:

- Events
- Effects
- States

---

## Decision

History stores Events only.

Effects are derived.

The structure is:

$$
History
\rightarrow
Event
\rightarrow
Effect
\rightarrow
State
$$

not:

$$
History
\rightarrow
State
$$

---

## Required Addition

Add:

**Meaning:**

History preserves Events.
Effects are reconstructed through the Effect Function.

---

# Issue 3: Event Space and Domain Layer Relationship

## Current Problem

Formal Core defines:

$$
\mathcal{E}
$$

Accounting Layer defines:

$$
\mathcal{E}_{acc}
$$

but the relationship is not explicit.

---

## Required Revision

Introduce:

$$
\mathcal{E}_{acc}
\subseteq
\mathcal{E}
$$

Meaning:

Accounting Events are specialized Events.

---

# Issue 4: Effect Space Definition

## Current Problem

ASM uses:

$$
\Delta\mathcal{S}
$$

as State Change Space.

However, the mathematical meaning is unclear.

For numerical systems:

$$
\Delta S=S_2-S_1
$$

is possible.

However, general systems may not have subtraction.

Example:

$$
Todo\rightarrow Doing
$$

does not naturally produce a vector difference.

---

## Required Direction

Formal Core should define Effect abstractly.

Possible direction:

```text
Effect Space represents possible state transformations or state changes
without assuming numerical subtraction.
```

Accounting Layer can specialize:

$$
(\Delta A,\Delta L,\Delta E)
$$

---

# Issue 5: Flow Definition Belongs to Domain Layer

## Current Problem

Formal Core currently defines:

$$
Flow(\tau)
=
\sum_{(e,t)\in H_\tau}
\alpha(e)
$$

However, general Effects cannot always be summed.

Example:

$$
Todo\rightarrow Doing
$$

cannot be aggregated mathematically.

---

## Required Revision

Remove Flow from Formal Core.

Move Flow definitions to domain layers.

Example:

Accounting Layer:

$$
Flow
=
Aggregation(Effects)
$$

---

# Issue 6: Representation Function Inconsistency

## Current Problem

Different documents use different definitions.

Old:

$$
F_Q:
(\mathcal{H},\mathcal{S})
\rightarrow
\mathcal{Y}_Q
$$

New:

$$
F_Q:
\mathcal{X}_Q
\rightarrow
\mathcal{Y}_Q
$$

---

## Decision

Use:

$$
F_Q:
\mathcal{X}_Q
\rightarrow
\mathcal{Y}_Q
$$

Reason:

Representations may require different input spaces.

Examples:

Balance Sheet:

$$
BS:
\mathcal{S}_{acc}
\rightarrow
\mathcal{Y}_{BS}
$$

Income Statement:

$$
IS:
\mathcal{F}_{acc}
\rightarrow
\mathcal{Y}_{IS}
$$

---

# Issue 7: Constraint Function Generalization

## Current Problem

Current definition:

$$
\kappa:
\mathcal{S}
\rightarrow
\mathbb{R}
$$

assumes one constraint.

Real systems have multiple constraints.

Examples:

Accounting Equation:

$$
A-L-E=0
$$

Double Entry:

$$
Debit-Credit=0
$$

---

## Required Revision

Generalize Constraint.

Possible:

$$
\kappa:
\mathcal{S}
\rightarrow
\mathcal{C}
$$

where:

$$
\mathcal{C}
$$

represents Constraint Space.

---

# Issue 8: Symbol Collision

## Current Problem

Event Space:

$$
\mathcal{E}
$$

and Equity:

$$
E
$$

are visually conflicting.

Event is a fundamental concept in ASM.

---

## Required Revision

Rename Equity.

Candidates:

$$
Eq
$$

or:

$$
Q
$$

Avoid:

$$
E
$$

for Equity.

---

# Issue 9: Observation Relation Direction

## Current Problem

Definitions conflict.

Some documents use:

$$
Obs\subseteq\mathcal{R}\times\mathcal{Z}
$$

Others reverse the order.

---

## Decision

Use:

$$
Obs\subseteq\mathcal{R}\times\mathcal{Z}
$$

Reason:

The conceptual direction is:

$$
Reality
\rightarrow
Evidence
$$

---

# Issue 10: Markdown Structure Standardization

## Current Problem

Documents use inconsistent Markdown styles.

Examples:

- mixed heading styles
- inconsistent Definition formatting
- inconsistent bold labels
- duplicated sections

---

## Required Standard

All ASM documents should follow:

```text

# Title

## Section

### Concept Name

**Definition:**

text

**Symbol:**

$$
x
$$

**Formal expression:**

$$
...
$$

**Meaning:**

text

**Consequence:**

text
```

---

# Issue 11: Lean Formalization Preparation

## Current Problem

ASM is not ready for Lean formalization.

The reason is not conceptual weakness.

The mathematical objects and dependencies are not yet stabilized.

---

## Required Order

Do not introduce Lean immediately.

First create:

$$
ASM\ Formal\ Core\ v2.0
$$

Recommended structure:

```text
ASM/
├── core/
│   ├── spaces.md
│   ├── functions.md
│   ├── axioms.md
│   ├── theorems.md
│   └── constraints.md
│
├── accounting/
│   ├── state.md
│   ├── event.md
│   ├── effect.md
│   └── representation.md
│
└── examples/
```

After stabilization:

1. Python consistency validator
2. Symbol checker
3. Formula checker
4. Lean formalization

---

# Priority Order

## Priority 1: Fundamental Corrections

1. State Generation Function
2. Effect Space Definition
3. Representation Function
4. Symbol collision

---

## Priority 2: Formal Core Refinement

1. Constraint generalization
2. Flow removal from Core
3. Layer relationship definitions

---

## Priority 3: Tooling

1. Markdown validator
2. Mathematical consistency checker
3. Lean preparation

---

# Recommended Development Process

## Step 1

Freeze ASM v1.x.

Do not continue manual patching individual files.

---

## Step 2

Create:

$$
ASM\ Formal\ Core\ v2.0
$$

Resolve:

- notation
- definitions
- axioms
- theorem dependencies

---

## Step 3

Create automated validation.

Validator checks:

```text

- undefined symbols
- duplicate symbols
- inconsistent formulas
- broken references
- glossary mismatch
```

---

## Step 4

Introduce Lean only after the mathematical model stabilizes.

---

# Final Assessment

ASM's fundamental architecture remains valid.

The current issue is not a failure of the model.

The situation is:

"An initially simple mathematical framework has expanded and now requires
formal refactoring."

The recommended evolution path is:

$$
ASM\ v1.x
\rightarrow
ASM\ Formal\ Core\ v2.0
\rightarrow
Validator
\rightarrow
Lean
$$
