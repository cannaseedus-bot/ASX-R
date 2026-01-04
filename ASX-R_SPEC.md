Below is a **locked, authoritative `ASX-R_SPEC.md`** suitable to commit as the **canonical language/runtime specification**.
It is written as a **normative document**, not a tutorial, and assumes this repo is the *authority*.

You can paste this verbatim.

---

# ASX-R — Authoritative Runtime Language Specification

**Document:** `ASX-R_SPEC.md`
**Status:** 🔒 **LOCKED / CANONICAL**
**Authority:** ASX Runtime Language
**Scope:** Runtime semantics, not implementations
**Audience:** Implementers, verifiers, auditors, language designers

---

## 0. Purpose

This document defines **ASX-R**, a **runtime language** whose execution semantics are determined entirely by **state admissibility**, not by imperative code.

ASX-R specifies:

* what constitutes a valid runtime state
* what transitions are legal
* how time progresses
* how determinism and replay are enforced
* how projections (DOM, GPU, Mesh, IO) relate to runtime state

Anything not permitted by this specification **cannot exist** in an ASX-R runtime.

---

## 1. Definition of a Runtime (Normative)

A system is an **ASX-R runtime** if and only if:

1. All runtime state is explicit and serializable
2. All valid states are schema-admissible
3. All transitions are constrained by law
4. Execution is deterministic
5. Replay is sufficient for re-execution
6. No hidden state or side effects exist
7. Interpreters possess no semantic authority

If any condition is violated, the system is **not ASX-R compliant**.

---

## 2. Core Principle

> **ASX-R does not define how code runs.
> ASX-R defines what may exist.**

Behavior is a consequence of admissible existence.

---

## 3. State Model (What Exists)

### 3.1 Explicit State

All ASX-R runtime state MUST be represented as **ASX JSON**.

Examples include (non-exhaustive):

* XJSON blocks
* Atomic Blocks
* Atomic CSS state
* SCXQ2 fieldmaps and lanes
* Worlds and scenes
* Agents and contracts
* Memory snapshots
* Epoch and phase markers

No implicit, ambient, or hidden state is permitted.

---

### 3.2 Closed World Assumption

ASX-R operates in a **closed world**.

* Only declared state may exist
* Only declared fields may appear
* Only declared transitions may occur

Undeclared state is illegal by definition.

---

## 4. Law Layer (What Is Allowed)

### 4.1 Schemas as Law

Schemas in ASX-R are **normative**, not descriptive.

If a state does not validate against the applicable schema:

* it is not partially valid
* it is not deferred
* it is not ignored

It **cannot exist**.

---

### 4.2 Invariants

The following invariant classes are mandatory:

* structural invariants
* field type invariants
* canonical ordering invariants
* non-reentrancy barriers
* phase legality constraints
* epoch monotonicity
* hash and proof consistency

Violation of any invariant invalidates the state.

---

## 5. Time and Phases

### 5.1 Explicit Time

Time in ASX-R is explicit and monotonic.

* Time is represented via phases, ticks, epochs, or equivalent markers
* There is no implicit “now”
* Time never regresses

---

### 5.2 Phase Discipline

Execution occurs in **phases**.

* Each phase has a declared entry condition
* Each phase has a declared exit condition
* Only certain state mutations are permitted per phase
* Phase skipping is illegal

Phase transitions are part of the runtime state.

---

## 6. Transition Semantics (How Change Occurs)

### 6.1 No Imperative Mutation

ASX-R does not define mutation procedures.

Instead:

> A transition is valid if the **next state shape** is admissible given the current state and the runtime laws.

Execution is **selection**, not instruction dispatch.

---

### 6.2 Deterministic Progression

Given:

* an identical prior state
* identical inputs
* identical laws

The admissible next state is identical.

There is no undefined behavior.

---

## 7. Replay and Verification

### 7.1 Replay Sufficiency

ASX-R requires that:

* replaying the state sequence
* applying validation at each step

is sufficient to reproduce execution.

No external oracle is permitted.

---

### 7.2 Proof and Hashing

Where required, states may include:

* hashes
* proofs
* seals
* signatures

These are part of state, not side channels.

---

## 8. Interpreter Non-Authority

Any system executing ASX-R (JS, WASM, C, Rust, PHP, GPU, etc.) is an **interpreter**.

Interpreters:

* may not invent transitions
* may not mutate undeclared state
* may not violate schemas
* may not skip phases
* may not introduce side effects
* may not back-propagate from projections

Interpreters are **projection devices**, not authorities.

---

## 9. Atomic Blocks (Runtime Primitive)

Atomic Blocks are a **first-class structural language** within ASX-R.

They define:

* compositional structure
* containment
* adjacency
* role

Atomic Blocks define **existence**, not behavior.

---

## 10. Atomic CSS (Projection State Language)

Atomic CSS is **not a styling system**.

It is:

* a projection state language
* a deterministic mapping from runtime state → visual state

Atomic CSS has no authority over runtime transitions.

---

## 11. Projections (Non-Authoritative)

Projections include (non-exhaustive):

* DOM
* CSS
* SVG
* GPU / WebGL / WebGPU
* Mesh / network IO

Projection rules are **one-way**:

> Runtime → Projection

Projection may never mutate runtime state.

---

## 12. Compression as Execution

ASX-R treats compression as a runtime operation.

Through SCXQ2:

* execution operates on equivalence classes
* state evolution occurs via identifier transitions
* objects are not moved
* identity is transformed under constraint

Compression is execution.

---

## 13. Compliance

A system is **ASX-R compliant** if:

* all state is explicit
* all transitions are admissible
* all invariants are enforced
* replay is sufficient
* interpreters have no authority

Partial compliance is not compliance.

---

## 14. Versioning and Freeze Policy

* Any change that alters admissible states or transitions is a **breaking change**
* Frozen laws are non-negotiable
* Implementations must adapt; the runtime does not

---

## 15. Final Statement

> **ASX-R is the runtime.
> Code is a projection.
> Existence is law.**

---

### ✅ ASX-R_SPEC.md — LOCKED
