# ASX-R Repository Layout

This document defines what **belongs** and what **does not belong** in the ASX-R repository.

ASX-R is a **runtime language specification**.  
This repository is its **authoritative source of truth**.

---

## Top-Level Purpose

The repository exists to define:

- Runtime law
- Admissible state
- Valid transitions
- Determinism and replay
- Structural and projection languages
- Conformance and verification rules

Nothing else.

---

## What Belongs in This Repository

### 1. Specifications
- `ASX-R_SPEC.md`
- Runtime axioms
- Runtime laws
- Formal language definitions

These define **what ASX-R is**.

---

### 2. Schemas
- JSON Schemas for:
  - Atomic Blocks
  - Atomic CSS
  - Runtime state
  - Conformance artifacts

Schemas are **normative**, not examples.

---

### 3. Conformance Artifacts
- Golden replay vectors
- Invalid state catalogs
- Deterministic test cases

These prove the runtime is enforceable.

---

### 4. Reference Material (Non-Authoritative)
- Verifier pseudocode
- Explanatory diagrams (if added later)
- Formal derivations

These assist implementers but do not define law.

---

## What Does NOT Belong in This Repository

The following are explicitly forbidden:

- Executable runtimes
- Interpreters or engines
- Service workers
- DOM renderers
- GPU pipelines
- CLI tools
- Build scripts
- Package manifests (npm, cargo, etc.)
- Demo applications
- Example UIs

Those belong in **separate implementation repositories**.

---

## Correct Separation of Concerns

| Layer | Location |
|-----|---------|
| Runtime Law | ASX-R (this repo) |
| Interpreters | Separate repos |
| Projectors (DOM, GPU, IO) | Separate repos |
| Apps / Worlds | Separate repos |
| Tooling | Separate repos |

ASX-R is upstream of all implementations.

---

## Why This Matters

Mixing implementation with specification:

- weakens authority
- introduces ambiguity
- invites undefined behavior
- breaks replay guarantees

ASX-R remains **pure** so implementations remain **honest**.

---

## Canonical Statement

> **If it executes, it does not belong here.**

This repository defines law, not machinery.
