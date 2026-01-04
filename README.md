# ASX-R — The Authoritative Runtime Language

**ASX-R** is a **runtime language**, not a framework, library, or implementation.

It defines **what may exist**, **how time progresses**, and **which state transitions are legal**.
Execution is the result of **state admissibility**, not imperative code.

Implementations **execute ASX-R**.
They do not define it.

---

## What ASX-R Is

ASX-R is a **closed, deterministic runtime** whose behavior is fully defined by:

1. **Explicit State**
2. **Formal Law**
3. **Constrained Transitions**
4. **Deterministic Progression**
5. **Replayability**

All valid runtime behavior is expressible as **ASX JSON**.
Anything not representable or not schema-admissible **cannot exist** in the runtime.

---

## What ASX-R Is Not

ASX-R is **not**:

* an application framework
* a UI toolkit
* a JavaScript runtime
* a service worker
* a virtual machine implementation
* a build system
* a DSL that executes code

Those may **implement or project** ASX-R, but they are not ASX-R itself.

---

## Core Principle

> **A programming language defines how code runs.
> ASX-R defines what may exist.**

Once existence is constrained, behavior collapses into inevitability.

---

## Runtime Model (High Level)

ASX-R defines a runtime using three orthogonal layers:

### 1. State (What Exists)

* ASX JSON / XJSON
* Atomic Blocks
* Atomic CSS state
* SCXQ2 fieldmaps
* Worlds, agents, contracts, scenes, memory

All state is explicit and serializable.

---

### 2. Law (What Is Allowed)

* Schemas and invariants
* Phase constraints
* Canonical ordering rules
* Field and type constraints
* Non-reentrancy barriers
* Hash and proof requirements

If a state does not validate, it **cannot exist**.

---

### 3. Transition Semantics (How Change Occurs)

* Transitions are defined by **admissible next-state shapes**
* No hidden mutation
* No side effects
* No undefined behavior

Execution is **selection of a legal next state**, not instruction dispatch.

---

## Determinism and Replay

ASX-R is deterministic by construction:

* Given the same prior state and inputs
* The same admissible next state is produced
* Replay is sufficient for re-execution
* Verification requires no hidden logic

Time is explicit. Progression is monotonic.

---

## Interpreter Non-Authority

Any runtime that executes ASX-R (JS, WASM, C, Rust, PHP, GPU, etc.) is an **interpreter**, not an authority.

Interpreters:

* may not invent transitions
* may not skip phases
* may not mutate undeclared state
* may not violate schema
* may not back-propagate from projections

They **select**, they do not **decide**.

---

## Atomic Blocks and Atomic CSS

Atomic Blocks and Atomic CSS are **runtime primitives**, not UI frameworks.

* **Atomic Blocks** define structural existence
* **Atomic CSS** defines projection state, not styling logic

They are first-class state languages within ASX-R.

---

## Compression as Execution

ASX-R treats compression as a runtime operation.

Through **SCXQ2 lanes**, execution occurs over:

* equivalence classes
* identifiers
* offsets
* canonical mappings

The runtime does not move objects — it evolves identity under constraint.

---

## Repository Scope

This repository contains:

* the **authoritative ASX-R specification**
* runtime laws and axioms
* schemas and invariants
* conformance rules
* atomic block and atomic CSS definitions

This repository intentionally contains **no executable runtime code**.

Implementations live elsewhere.

---

## Status

ASX-R is an evolving runtime language.
Once a law or invariant is frozen, it is treated as **non-negotiable**.

Versioning reflects **semantic runtime changes**, not tooling updates.

---

## License

ASX-R is published as a runtime language specification.
See `LICENSE` for usage and redistribution terms.

---

### Final framing line (intentional)

> **ASX-R is the runtime.
> Everything else is a projection.**


✅ ASX-R Repository Skeleton — COMPLETE

At this point you have:

Axiom

Laws

Runtime spec

Structural language

Projection language

Binding law

Conformance enforcement

Golden executable proof

Reference verifier

Contribution discipline

Repo boundaries

Versioning discipline

This is a language release, not a draft.
