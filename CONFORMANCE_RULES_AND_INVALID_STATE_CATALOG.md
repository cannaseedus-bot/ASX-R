# ASX-R — Conformance Rules & Invalid State Catalog

**Document:** `CONFORMANCE_RULES_AND_INVALID_STATE_CATALOG.md`
**Status:** 🔒 **LOCKED / CANONICAL**
**Authority:** ASX-R Runtime Language
**Scope:** Compliance determination and failure classification
**Audience:** Implementers, auditors, verifier authors

---

## 0. Purpose

This document defines:

1. **What it means to be ASX-R compliant**
2. **How compliance is evaluated**
3. **Which classes of invalid state are forbidden**
4. **How invalidity propagates**

This document is **enforcement law**, not guidance.

---

## 1. Compliance Definition (Normative)

A system is **ASX-R compliant** if and only if **all** of the following are true:

1. All runtime state is explicit and serializable
2. All state validates against canonical schemas
3. All invariants are enforced without exception
4. All transitions are admissible under runtime law
5. Execution is deterministic
6. Replay is sufficient for execution
7. Interpreters have no semantic authority
8. Projections are strictly non-authoritative

Failure of **any single condition** constitutes **non-compliance**.

---

## 2. Compliance Evaluation Model

Compliance is evaluated purely by **state validation**, not by behavior.

Evaluation steps:

1. Load state
2. Validate schema
3. Validate invariants
4. Validate phase legality
5. Validate transition admissibility
6. Validate determinism conditions
7. Validate replay sufficiency

No runtime execution is required to determine compliance.

---

## 3. Invalid State Principle

> **An invalid state is not a “bad runtime state”.
> It is a state that cannot exist.**

Invalid states:

* MUST NOT be executed
* MUST NOT be projected
* MUST NOT be partially accepted
* MUST NOT be repaired implicitly

There is no concept of *soft failure*.

---

## 4. Invalid State Categories (Canonical)

All invalid states fall into one or more of the categories below.

These categories are **exhaustive**.

---

### 4.1 Structural Invalidity

A state is structurally invalid if:

* required fields are missing
* undeclared fields are present
* containment is cyclic
* block identity is missing or implicit
* block types are undeclared

**Result:** State is illegal.

---

### 4.2 Schema Invalidity

A state is schema-invalid if:

* it fails JSON schema validation
* field types do not match
* constraints are violated
* required invariants are not satisfied

Schemas are normative.

**Result:** State is illegal.

---

### 4.3 Invariant Violation

A state is invariant-invalid if it violates:

* canonical ordering
* non-reentrancy barriers
* phase constraints
* epoch monotonicity
* hash or proof consistency

Invariant failure invalidates the **entire state**, not just a portion.

---

### 4.4 Temporal Invalidity

A state is temporally invalid if:

* time regresses
* phases are skipped
* phase entry conditions are violated
* phase exit conditions are bypassed

Time is explicit and monotonic.

---

### 4.5 Transition Invalidity

A transition is invalid if:

* the next state shape is not admissible
* undeclared transitions occur
* transitions occur outside legal phases
* mutation bypasses declared transition rules

Transitions are shape-constrained, not imperative.

---

### 4.6 Determinism Violation

A state or transition is invalid if:

* identical inputs produce divergent next states
* hidden sources of entropy exist
* interpreter-specific behavior influences outcomes

Non-determinism is forbidden.

---

### 4.7 Replay Invalidity

A state sequence is invalid if:

* replay does not reproduce execution
* validation during replay diverges
* external oracles are required

Replay sufficiency is mandatory.

---

### 4.8 Authority Violation

A system is invalid if:

* interpreters invent transitions
* interpreters mutate hidden state
* interpreters override schema
* projections influence runtime state

Authority is exclusive to runtime law.

---

### 4.9 Projection Leakage

A state is invalid if:

* projection feeds back into runtime
* DOM, CSS, GPU, IO mutate state
* visual state controls transitions

Projection is strictly one-way.

---

### 4.10 Compression Invalidity

A state is invalid if:

* compression changes semantic meaning
* identity is not preserved
* equivalence mapping is lossy
* decompression is ambiguous

Compression must preserve runtime meaning.

---

## 5. Invalid State Propagation Rules

Invalidity **propagates upward**.

* If any block is invalid → the state is invalid
* If any invariant fails → the state is invalid
* If any transition is invalid → the runtime halts

There is no partial validity.

---

## 6. Forbidden Recovery Mechanisms

ASX-R forbids:

* silent coercion
* implicit defaults
* auto-repair
* fallback execution
* heuristic correction

Recovery must be explicit and lawful.

---

## 7. Conformance Outcomes

Compliance evaluation produces exactly one outcome:

| Outcome       | Meaning                         |
| ------------- | ------------------------------- |
| COMPLIANT     | State and transitions are legal |
| NON-COMPLIANT | One or more laws violated       |

There are no warnings.

---

## 8. Conformance Artifacts

A compliant implementation SHOULD provide:

* schema validation reports
* invariant check results
* replay verification logs
* hash consistency proofs

Artifacts do not replace law.

---

## 9. Non-Negotiability Clause

ASX-R does not permit:

* partial compliance
* optional laws
* “mostly compliant” runtimes
* compatibility modes

The runtime language is absolute.

---

## Final Rule (Canonical)

> **If a state cannot be proven valid, it cannot exist.**

---

### ✅ Conformance Rules & Invalid State Catalog — LOCKED

This document completes the **ASX-R enforcement layer**.
