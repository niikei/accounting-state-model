# ASM Double Entry v1.1

## Purpose

This document defines the relationship between Double Entry and the
Accounting State Model (ASM).

The purpose is to explain Double Entry as a representation mechanism of
Accounting Effects.

ASM does not treat Journal Entries as the source of accounting meaning.

Instead, Journal Entries represent changes that have already been defined
at the Accounting Effect layer.

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

Double Entry is introduced as a representation of Accounting Effects:

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

Double Entry is a representation system that expresses an Accounting
Effect through balancing components.

Its purpose is to preserve accounting constraints when representing state
changes.

Double Entry belongs to the representation layer.

It does not define the economic event or the Accounting Effect itself.

---

## Journal Representation

A Journal Entry represents an Accounting Effect.

The Journal Representation Function is:

$$
J:
\Delta\mathcal{S}_{acc}
\rightarrow
\mathcal{Y}_{journal}
$$

where:

- $\Delta\mathcal{S}_{acc}$ represents Accounting Effects.
- $\mathcal{Y}_{journal}$ represents Journal Representation Space.

A Journal Representation is generated from an Accounting Effect:

$$
j
=
J(\alpha_{acc}(e_{acc}))
$$

The Journal Entry is a representation of the Effect.

It does not create the Effect.

---

## Double Entry Constraint

A Journal Representation must preserve the Double Entry constraint.

Let:

$$
D(j)
$$

represent the total Debit coordinates of a Journal Representation.

Let:

$$
C(j)
$$

represent the total Credit coordinates of a Journal Representation.

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

These are different constraints.

The Accounting Equation defines valid Accounting States.

The Double Entry Constraint defines valid Journal Representations.

Therefore:

$$
Accounting\ State\ Constraint
\neq
Journal\ Representation\ Constraint
$$

---

## Effect and Journal Representation

An Accounting Effect may be represented by a Journal Entry.

For:

$$
\alpha_{acc}(e)
\in
\Delta\mathcal{S}_{acc}
$$

the Journal Representation is:

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

The Journal Entry expresses the Effect.

It does not generate the Effect.

---

## Debit and Credit as Representation Coordinates

Debit and Credit are not independent economic realities.

They are coordinates used to represent Accounting Effects.

Therefore:

$$
Debit/Credit
\in
Representation\ Coordinate\ System
$$

Debit and Credit describe how an Effect is represented.

They do not describe the original economic occurrence.

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

- account dimensions
- debit and credit coordinates
- journal entry structure
- ledger representation

This document defines only the conceptual relationship between
Accounting Effect and Double Entry.

---

## Summary

Double Entry is a representation mechanism for Accounting Effects.

The fundamental structure is:

$$
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Journal\ Representation
$$

ASM separates:

- economic cause
- accounting effect
- journal representation

Therefore:

$$
\boxed{
Double\ Entry\ represents\ accounting\ state\ changes,\ but\ does\ not\ create\ them
}
$$
