# ASX-R Changelog

All notable changes to the ASX-R runtime language are documented here.

ASX-R follows **semantic runtime versioning**, not tooling versioning.

---

## Versioning Rules

- **MAJOR** — Runtime semantics change  
  (admissible states or transitions change)

- **MINOR** — Backward-compatible extension  
  (new schemas, new conformance artifacts, no weakening of law)

- **PATCH** — Clarification only  
  (wording, formatting, references, no semantic change)

If runtime behavior changes, the **MAJOR version increments**.

---

## [Unreleased]

- None

---

## [1.0.0] — Initial Canonical Release

### Added
- JSON Runtime Axiom (frozen)
- ASX-R Runtime Laws (frozen)
- ASX-R Specification (locked)
- Atomic Block Language (formal spec)
- Atomic CSS Runtime (formal spec)
- Atomic Block ↔ Atomic CSS Binding Spec
- Conformance Rules & Invalid State Catalog
- Minimal Golden Replay Vector Set
- Reference Verifier Pseudocode

### Status
- Runtime semantics **locked**
- Closed-world guarantees enforced
- Deterministic replay proven

---

## Change Policy

Once a law or axiom is frozen:

- It is never modified
- It may only be superseded by a **new major version**
- Implementations must adapt

---

## Canonical Reminder

> **ASX-R versions track reality constraints,  
> not convenience or implementation maturity.**
