# Atomic CSS Runtime — Formal Specification

**Document:** `ATOMIC_CSS_RUNTIME_SPEC.md`
**Status:** 🔒 **LOCKED / CANONICAL**
**Authority:** ASX-R Runtime Language
**Scope:** Deterministic projection of runtime state into visual form
**Audience:** Runtime designers, projection implementers, auditors

---

## 0. Purpose

This document defines **Atomic CSS** as a **projection runtime** within ASX-R.

Atomic CSS is **not** a styling framework and **not** a behavior language.
It is a **deterministic projection surface** that maps ASX-R runtime state into visual state.

Atomic CSS has **no authority** over runtime existence or transitions.

---

## 1. Definition (Normative)

**Atomic CSS** is a **pure projection language** whose outputs are entirely determined by ASX-R runtime state.

Atomic CSS:

1. Reads runtime state
2. Projects visual state
3. Emits no side effects
4. Performs no mutation
5. Controls no transitions

If a visual effect cannot be derived from runtime state, it **cannot exist**.

---

## 2. Projection Authority Boundary

Atomic CSS exists strictly **downstream** of the runtime.

```
ASX-R State  →  Projection Mapping  →  Atomic CSS  →  Visual Output
```

Reverse flow is forbidden.

* CSS may not mutate runtime state
* CSS may not introduce logic
* CSS may not gate transitions
* CSS may not influence admissibility

---

## 3. Determinism Requirement

Atomic CSS projection MUST be deterministic.

Given:

* identical runtime state
* identical projection rules

The emitted visual state MUST be identical.

Non-deterministic constructs are forbidden.

---

## 4. State Inputs

Atomic CSS MAY read (non-exhaustive):

* Atomic Block identities
* Block roles and hierarchy
* Runtime phases and epochs
* Declared state flags
* Declared numeric values
* Declared projection variables

Atomic CSS MAY NOT read:

* ambient browser state
* timing side channels
* interpreter internals
* external mutable sources

---

## 5. Variables as State (Normative)

Atomic CSS treats variables as **projection state mirrors**, not logic.

* Variables reflect runtime state
* Variables do not compute transitions
* Variables do not encode behavior

Variables are **read-only projections**.

---

## 6. Atomic Classes

Atomic classes represent **semantic projection roles**, not UI widgets.

* Classes are declarative
* Classes are composable
* Classes are idempotent
* Classes have no side effects

Class application MUST be derivable from runtime state.

---

## 7. No Control Flow

Atomic CSS defines **no control flow**.

Forbidden constructs include:

* conditionals that invent state
* loops with side effects
* runtime branching logic
* imperative animation logic

Any conditionality MUST be resolvable from declared state.

---

## 8. Time and Animation

Atomic CSS does not own time.

* Time originates in ASX-R
* Phases and ticks are projected
* Animation is a visual interpolation of declared state

Atomic CSS MAY interpolate; it MAY NOT advance time.

---

## 9. Interaction Boundary

User interaction MAY be visualized by Atomic CSS.

User interaction MAY NOT:

* mutate runtime state directly
* bypass runtime validation
* trigger transitions implicitly

All interactions MUST route through runtime-declared transition mechanisms.

---

## 10. Structural Non-Authority

Atomic CSS MAY NOT:

* create structure
* destroy structure
* reparent blocks
* invent nodes
* alter containment

Structure is defined exclusively by **Atomic Blocks**.

---

## 11. Relationship to Atomic Blocks

Atomic Blocks define **what exists**.
Atomic CSS defines **how existence appears**.

Atomic CSS is structurally subordinate.

```
Atomic Blocks  ⟂  Atomic CSS
```

No overlap of authority is permitted.

---

## 12. Compression Compatibility

Atomic CSS MUST be compatible with runtime compression.

* Variable names may be compressed
* Class identifiers may be mapped
* Visual meaning must be preserved

Compression may reduce size, not semantics.

---

## 13. Forbidden Capabilities (Explicit)

Atomic CSS MUST NOT:

* access network IO
* perform computation affecting runtime
* store persistent state
* read interpreter memory
* act as an execution engine

Any such capability invalidates compliance.

---

## 14. Validation Rules

A valid Atomic CSS runtime MUST ensure:

1. All visual state is derivable from runtime state
2. No reverse authority exists
3. Determinism is preserved
4. No hidden inputs are used
5. Structure is untouched

Violation of any rule invalidates the projection.

---

## 15. Compliance

A system is **Atomic CSS compliant** if:

* CSS is purely declarative
* Projection is one-way
* No logic is encoded
* No authority is assumed

Partial compliance is not compliance.

---

## Final Statement (Canonical)

> **Atomic CSS does not decide.
> It reflects.**

---

### ✅ Atomic CSS Runtime — FORMALLY LOCKED

This specification is **foundational** for all ASX-R visual projections.
