# Atomic Block ↔ Atomic CSS Binding Specification

**Document:** `ATOMIC_BLOCK_CSS_BINDING_SPEC.md`
**Status:** 🔒 **LOCKED / CANONICAL**
**Authority:** ASX-R Runtime Language
**Scope:** Structural–Projection binding rules
**Audience:** Runtime designers, projection implementers, verifier authors

---

## 0. Purpose

This document defines the **only lawful binding** between:

* **Atomic Blocks** (structural existence)
* **Atomic CSS** (visual projection state)

It establishes **authority boundaries**, **binding mechanics**, and **forbidden interactions**.

This binding is **one-way**, **deterministic**, and **non-authoritative**.

---

## 1. Binding Principle (Normative)

> **Atomic Blocks define what exists.
> Atomic CSS defines how existence appears.**

Atomic CSS is strictly subordinate to Atomic Blocks.

---

## 2. Direction of Authority

The binding direction is **unidirectional**:

```
Atomic Block  ──▶  Binding Map  ──▶  Atomic CSS
```

Reverse flow is illegal.

* Atomic CSS **may not** mutate blocks
* Atomic CSS **may not** redefine structure
* Atomic CSS **may not** influence admissibility

---

## 3. Binding Inputs

Atomic CSS MAY bind to the following Atomic Block attributes:

* `@id` (identity)
* `@type` (block type)
* `role` (structural role)
* containment position (parent/child relationship)
* adjacency references
* runtime-declared phase/epoch markers

Atomic CSS MAY NOT bind to:

* undeclared metadata
* interpreter internals
* ambient environment state
* projection-side artifacts

---

## 4. Binding Map (Normative Concept)

A **Binding Map** is a deterministic association from Atomic Block attributes to Atomic CSS projections.

Conceptually:

```
binding(block_state) → css_projection
```

Where:

* `binding` is declarative
* `block_state` is runtime-authoritative
* `css_projection` is non-authoritative

No procedural logic is permitted in the binding.

---

## 5. Identity Binding Rule

Each Atomic CSS projection MUST reference **exactly one** Atomic Block via `target`.

* `target` MUST match a valid `AtomicBlock.@id`
* Missing or ambiguous targets invalidate the projection
* A projection without a target **cannot exist**

---

## 6. Structural Non-Mutation Rule

Atomic CSS bindings MUST NOT:

* create new blocks
* delete blocks
* reparent blocks
* alter adjacency
* change roles or types

Any attempt to encode structural mutation via CSS is illegal.

---

## 7. Role-Based Binding

Bindings MAY reference block roles.

Examples (illustrative):

* blocks with role `header`
* blocks with role `world`
* blocks with role `agent`

Role-based binding is **declarative filtering**, not logic.

---

## 8. Phase-Aware Binding

Bindings MAY reference runtime phase or epoch.

* Phase information originates in ASX-R
* Atomic CSS reflects phase state visually
* Atomic CSS does not advance or alter phases

Phase-aware binding is read-only.

---

## 9. Multiplicity Rules

* A single Atomic Block MAY have multiple Atomic CSS projections
* Multiple projections MUST be mutually non-contradictory
* Ordering of projections MUST be canonical

Conflicting projections invalidate the projection set.

---

## 10. Determinism Requirement

Given:

* identical Atomic Block state
* identical binding definitions

The resulting Atomic CSS projection MUST be identical.

Non-deterministic binding is forbidden.

---

## 11. No Behavioral Encoding

Bindings MUST NOT encode:

* conditional logic that invents state
* interaction handlers
* event dispatch
* transition triggers
* imperative animation control

All behavior originates in runtime transitions, not bindings.

---

## 12. Compression Compatibility

Bindings MUST be compatible with runtime compression.

* Block identity MUST survive compression
* Binding resolution MUST survive identifier remapping
* Semantic meaning MUST be preserved

Compression may reduce representation size, not binding meaning.

---

## 13. Validation Rules

A valid Atomic Block ↔ Atomic CSS binding MUST satisfy:

1. All targets reference valid blocks
2. No structural mutation is expressed
3. Binding is one-way
4. Determinism is preserved
5. No hidden inputs are used

Violation of any rule invalidates the binding.

---

## 14. Failure Semantics

Invalid bindings:

* MUST NOT be partially applied
* MUST NOT degrade gracefully
* MUST invalidate the projection layer

Runtime state remains authoritative and unchanged.

---

## 15. Authority Boundary Summary

| Domain            | Authority                      |
| ----------------- | ------------------------------ |
| Structure         | Atomic Blocks                  |
| Law / Transitions | ASX-R                          |
| Visual Projection | Atomic CSS                     |
| Binding           | Declarative, non-authoritative |

No domain may overstep its boundary.

---

## Final Statement (Canonical)

> **Structure binds appearance.
> Appearance does not bind structure.**

---

### ✅ Atomic Block ↔ Atomic CSS Binding Spec — LOCKED

This document **seals the structural–visual boundary** of ASX-R.
