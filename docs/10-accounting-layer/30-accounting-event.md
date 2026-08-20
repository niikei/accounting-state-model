# ASM Accounting Event v1.1

## Purpose

This document defines the concept of Accounting Event in the Accounting
Layer of the Accounting State Model (ASM).

The purpose is to define how economic occurrences become events within the
accounting model.

Accounting Event is the causal input that generates Accounting Effects
and changes Accounting State.

---

## Relationship with Formal Core

The Formal Core defines Event as:

$$
e\in\mathcal{E}
$$

An Event represents an occurrence that produces an Effect.

The Accounting Layer specializes this concept:

$$
e_{acc}\in\mathcal{E}_{acc}
$$

where:

- $e_{acc}$ represents an Accounting Event.
- $\mathcal{E}_{acc}$ represents Accounting Event Space.

---

## Economic Event and Accounting Event

An economic entity experiences many occurrences.

However, not every occurrence becomes an Accounting Event.

The relationship is:

$$
Economic\ Reality
\rightarrow
Evidence
\rightarrow
Accounting\ Event
$$

An Economic Event exists in reality.

An Accounting Event exists in the accounting model.

Therefore:

$$
Economic\ Event
\neq
Accounting\ Event
$$

---

## Accounting Event Definition

**Accounting Event:**

An Accounting Event is an occurrence recognized by the accounting model
as a cause of a state transition.

Formally:

$$
e_{acc}\in\mathcal{E}_{acc}
$$

An Accounting Event represents:

- a recognized occurrence
- an interpretation result
- a causal input for state transition

An Accounting Event is not raw Evidence.

It is an interpreted representation.

---

## Accounting Event Generation

Accounting Events are generated through Interpretation.

The Formal Core defines:

$$
I:
\mathcal{Z}
\times
\Theta
\times
\mathcal{M}
\rightarrow
\mathcal{E}
$$

The Accounting Layer specializes this:

$$
I_{acc}:
\mathcal{Z}_{acc}
\times
\Theta_{acc}
\times
\mathcal{M}_{acc}
\rightarrow
\mathcal{E}_{acc}
$$

Therefore:

$$
e_{acc}
=
I_{acc}(z,\theta,m)
$$

where:

- $z$ represents Evidence.
- $\theta$ represents Accounting Policy.
- $m$ represents Parameters or assumptions.

The Accounting Event is the result of interpretation.

It is not identical to Evidence, Policy, or Parameters.

---

## Recognition and Measurement

Accounting Event generation involves interpretation.

The same Evidence may produce different Accounting Events depending on:

- accounting policies
- estimates
- measurement rules

Formally:

$$
I_{acc}(z,\theta_1,m_1)
\neq
I_{acc}(z,\theta_2,m_2)
$$

may hold.

Therefore:

Accounting Event is not purely observed data.

It is an interpreted representation.

---

## Accounting Event and Effect

An Accounting Event is the cause of change.

The Accounting Effect is the resulting change.

The relationship is:

$$
e_{acc}
\rightarrow
\alpha_{acc}(e_{acc})
$$

where:

$$
\alpha_{acc}:
\mathcal{E}_{acc}
\rightarrow
\Delta\mathcal{S}_{acc}
$$

The distinction is:

**Accounting Event:**

"What occurred?"

**Accounting Effect:**

"What changed because of it?"

---

## Effect and Flow Relationship

An Accounting Effect represents an instantaneous change in Accounting
State.

The effect itself is:

$$
\alpha_{acc}(e_{acc})
\in
\Delta\mathcal{S}_{acc}
$$

Flow dimensions are obtained by aggregating Effects over a period.

For:

$$
I=[t_0,t_1]
$$

a Flow may be represented as:

$$
Flow(I)
=
\sum_{e\in H_I}
\alpha(e)
$$

Therefore:

$$
Effect
\neq
Flow
$$

Effect represents a single change.

Flow represents accumulated changes.

---

## Accounting Event History

Accounting Events are accumulated into Accounting History.

$$
H_{acc}(t)
\in
(\mathcal{E}_{acc}\times T)^*
$$

The History records:

- what Accounting Events occurred
- when they occurred

The Accounting State is derived from this History:

$$
S_{acc,t}
=
G_{acc}(H_{acc}(t))
$$

Therefore:

$$
Accounting\ Event
\rightarrow
Accounting\ History
\rightarrow
Accounting\ State
$$

---

## Event Ordering

Accounting Events exist in temporal order.

For:

$$
t_1<t_2
$$

the History preserves:

$$
(e_1,t_1)
\prec
(e_2,t_2)
$$

The ordering of Events is essential because State transitions are
sequential.

---

## Event Is Not a Record

Traditional accounting often begins with records such as Journal Entries.

ASM separates the causal layer from the representation layer.

The order is:

$$
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Journal\ Representation
$$

A Journal Entry represents an Accounting Effect.

It does not create the Accounting Event or the Accounting State
transition itself.

---

## Future Extension

The following concepts are introduced in later documents:

- Accounting Effect
- Measurement structure
- Double Entry representation
- Journal Entry

This document defines only the causal Event layer.

---

## Summary

An Accounting Event is an interpreted economic occurrence that causes a
change in Accounting State.

The fundamental structures are:

$$
Evidence
\rightarrow
Accounting\ Event
\rightarrow
Accounting\ History
\rightarrow
Accounting\ State
$$

and:

$$
Accounting\ Event
\rightarrow
Accounting\ Effect
\rightarrow
Accounting\ State
$$

ASM separates:

- Reality from Accounting Event
- Evidence from Accounting Event
- Accounting Event from Accounting Effect
- Accounting Effect from Representation

Therefore:

$$
\boxed{
Accounting\ Event\ is\ the\ causal\ unit\ of\ accounting\ state\ transition
}
$$
