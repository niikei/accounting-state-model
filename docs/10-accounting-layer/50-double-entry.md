# ASM Double Entry v1.2

## Purpose

This document defines the relationship between Double Entry and the
Accounting State Model (ASM).

The purpose is to explain Double Entry as a constrained representation
mechanism of Accounting Effects.

ASM does not treat Journal Entries as the source of accounting meaning.

Instead, Journal Entries represent Accounting Effects that have already
been defined at the Accounting Effect layer.

---

## Relationship with Accounting Effect

The Accounting Layer defines:

$$
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Accounting\ State
$$

Double Entry represents Accounting Effects:

$$
Accounting\ Effect
\rightarrow
Journal\ Representation
$$

Therefore:

$$
Double\ Entry
\neq
Accounting\ Effect
$$

Double Entry is a representation system for Accounting Effects.

---

## Double Entry Definition

**Double Entry:**

Double Entry is a constrained representation system that expresses an
Accounting Effect through balancing components.

Its purpose is to preserve accounting constraints while representing
state changes.

Double Entry belongs to the representation layer.

It does not define the economic occurrence or the Accounting Effect
itself.

---

## Journal Representation

A Journal Entry represents an Accounting Effect.

The Journal Representation Function is:

$$
J:
\Delta\mathcal{S}_{acc}
\rightarrow
\mathcal{J}
$$

where:

- $\Delta\mathcal{S}_{acc}$ represents Accounting Effects.
- $\mathcal{J}$ represents Journal Representation Space.

A Journal Representation is generated from an Accounting Effect:

$$
j
=
J(\alpha_{acc}(e_{acc}))
$$

The Journal Entry expresses the Effect.

It does not create the Effect.

---

## Double Entry Constraint

A Journal Representation must preserve the Double Entry constraint.

Let:

$$
D(j)
$$

represent total Debit coordinates.

Let:

$$
C(j)
$$

represent total Credit coordinates.

The Double Entry constraint is:

$$
D(j)-C(j)=0
$$

This constraint exists at the representation level.

It ensures that the Journal Representation consistently expresses the
underlying Accounting Effect.

---

## Relationship with Accounting Equation

The Accounting State constraint is:

$$
A-L-E=0
$$

The Double Entry constraint is:

$$
D(j)-C(j)=0
$$

These constraints exist at different layers.

The Accounting Equation defines valid Accounting States.

The Double Entry Constraint defines valid Journal Representations.

Therefore:

$$
Accounting\ State\ Constraint
\neq
Journal\ Representation\ Constraint
$$

However:

$$
Double\ Entry
\rightarrow
Constraint\ Preservation
$$

ensures that represented Effects remain consistent with Accounting
Structure.

---

## Effect and Journal Representation

An Accounting Effect:

$$
\alpha_{acc}(e)
\in
\Delta\mathcal{S}_{acc}
$$

is represented as:

$$
j
=
J(\alpha_{acc}(e))
$$

The causal direction is:

$$
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Journal\ Representation
$$

The Journal Entry describes the Effect.

It does not generate the Effect.

---

## Debit and Credit as Representation Coordinates

Debit and Credit are not independent economic realities.

They are coordinates used to represent Accounting Effects.

The mapping is:

$$
\Delta\mathcal{S}_{acc}
\rightarrow
\mathcal{J}
$$

Debit and Credit belong to the representation coordinate system.

Therefore:

$$
Debit/Credit
\neq
Economic\ Reality
$$

and:

$$
Debit/Credit
\neq
Accounting\ Event
$$

---

## Double Entry and State Transition

The actual Accounting State transition is:

$$
S_{acc,t+1}
=
\delta_{acc}
(
S_{acc,t},
\alpha_{acc}(e_{acc})
)
$$

The Journal Representation records the Effect:

$$
j
=
J(\alpha_{acc}(e_{acc}))
$$

Therefore:

$$
Journal
\rightarrow
State
$$

is not the fundamental relationship.

The fundamental relationship is:

$$
Effect
\rightarrow
State
$$

---

## Multiple Representations

A single Accounting Effect may have multiple representations.

For example:

$$
\alpha_{acc}(e)
$$

may generate:

- Journal Representation
- Financial Statement Representation
- Management Report Representation

Therefore:

$$
Effect
\rightarrow
Multiple\ Representations
$$

may hold.

This follows the Representation Principle of ASM.

---

## Future Extension

Future documents introduce:

- Account dimensions.
- Debit and Credit coordinates.
- Journal Entry structure.
- Ledger representation.

These concepts define the detailed representation of Accounting Effects.

---

## Summary

Double Entry is a constrained representation mechanism for Accounting
Effects.

The fundamental structure is:

$$
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Journal\ Representation
$$

ASM separates:

- economic occurrence
- Accounting Event
- Accounting Effect
- Journal Representation

Therefore:

$$
\boxed{
Double\ Entry\ represents\ accounting\ state\ changes,\ but\ does\ not\ create\ them
}
$$
