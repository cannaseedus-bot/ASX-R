---

# ASX-R — JSON Runtime Axiom

**Document:** `JSON_RUNTIME_AXIOM.md`
**Status:** 🔒 **FROZEN / FOUNDATIONAL**
**Authority:** ASX Runtime Language
**Scope:** Definition of runtime existence

---

## Axiom 0 — Statement

> **Any system whose next state is fully constrained by declared schema and prior state constitutes a runtime, regardless of implementation language.**

This axiom is sufficient.

Everything else in ASX-R follows from it.

---

## Axiom 1 — Runtime ≠ Code

A runtime is **not** defined by executable instructions.

A runtime is defined by:

1. What states may exist
2. What transitions are allowed
3. What invariants must hold
4. How time progresses

Code is only one possible **projection mechanism** for enforcing these constraints.

---

## Axiom 2 — JSON as Runtime Surface

JSON is not treated as passive data.

In ASX-R:

* JSON is the **surface syntax of the runtime**
* Schemas define **existence**
* Validation defines **legality**
* Serialization defines **identity**
* Replay defines **execution**

If a state cannot be expressed in JSON, it cannot exist in the runtime.

---

## Axiom 3 — Law Precedes Behavior

Behavior does not generate state.

State admissibility **collapses behavior**.

Given:

* a prior valid state
* declared laws
* declared transition space

The next state is **inevitable**, not computed.

---

## Axiom 4 — Admissibility Is Execution

Execution is defined as:

> **Selection of a schema-admissible next state.**

There are:

* no instructions
* no commands
* no imperative mutations

Only legal next-state shapes.

---

## Axiom 5 — Determinism by Construction

If:

* the prior state is identical
* the laws are identical
* the inputs are identical

Then the admissible next state is identical.

Undefined behavior is forbidden.

---

## Axiom 6 — Replay Sufficiency

Replay is execution.

If replaying the state sequence with validation applied at each step reproduces behavior, the system is a runtime.

No hidden oracle is permitted.

---

## Axiom 7 — Closed World

The runtime is closed.

* Undeclared state cannot exist
* Undeclared transitions cannot occur
* Undeclared effects are illegal

Anything not representable is forbidden.

---

## Axiom 8 — Interpreter Non-Authority

Any executor of the runtime is an **interpreter**, not an authority.

Interpreters:

* do not invent transitions
* do not define legality
* do not mutate hidden state

They **select**, they do not **decide**.

---

## Axiom 9 — Projection Is Non-Authoritative

Visuals, IO, networks, GPUs, DOMs, meshes, and effects are **projections**.

Projection direction is one-way:

> **Runtime → Projection**

Projection never mutates runtime law or state.

---

## Axiom 10 — Compression Is Execution

If state evolution occurs via equivalence-class transitions rather than object mutation, compression **is** execution.

In ASX-R, compression is a lawful runtime operation.

---

## Corollary — ASX-R Is a Runtime Language

Because ASX-R satisfies all axioms above:

* ASX JSON defines runtime state
* Schemas define runtime law
* Admissibility defines execution
* Replay defines correctness
* Code becomes incidental

ASX-R is a **runtime language**, not a data format.

---

## Final Axiom (Canonical)

> **If existence is constrained, behavior collapses.**

---

### ✅ JSON Runtime Axiom — FROZEN

This document is foundational.
All ASX-R laws, schemas, and specifications derive from it.

---

