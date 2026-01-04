# Contributing to ASX-R

ASX-R is a **runtime language specification**, not an implementation repository.

This project prioritizes **semantic correctness**, **determinism**, and **non-authority of tooling** over convenience or velocity.

If you are looking to add code, demos, or frameworks, this is **not** the correct repository.

---

## What Contributions Are Accepted

Contributions MUST fall into one of the following categories:

1. **Specification Clarification**
   - Clearer wording
   - Reduced ambiguity
   - Improved precision
   - Explicit edge-case coverage

2. **Formalization**
   - New schemas that enforce existing law
   - New invariants derived from existing axioms
   - Conformance rules that make implicit law explicit

3. **Conformance Artifacts**
   - Additional *minimal* golden replay vectors
   - New invalid-state examples that clarify enforcement
   - Verifier test cases (non-executable)

4. **Documentation Hygiene**
   - Typos
   - Formatting
   - Cross-references
   - Structural clarity

---

## What Contributions Are NOT Accepted

The following WILL be rejected:

- Executable runtime code
- Interpreters or engines
- JavaScript, WASM, Rust, Python, or C implementations
- UI frameworks or visual demos
- Performance optimizations
- “Developer experience” abstractions
- Optional or “relaxed” laws
- Partial-compliance modes
- Backwards-compatibility shims that weaken law

ASX-R defines **what must be true**, not how to make it convenient.

---

## Law Hierarchy (Read This First)

All contributions MUST respect this authority order:

1. **JSON Runtime Axiom**
2. **RUNTIME_LAWS.md**
3. **ASX-R_SPEC.md**
4. **Conformance Rules & Invalid State Catalog**
5. **Schemas**
6. **Golden Replay Vectors**
7. **Reference Verifier Pseudocode**

Lower items may not contradict higher items.

If a conflict exists, the contribution is invalid.

---

## Change Classification (Required)

Every contribution MUST declare its impact:

- **Clarification** — no semantic change
- **Restriction** — reduces the set of admissible states
- **Extension** — adds new admissible states *without weakening law*
- **Breaking** — changes runtime semantics (rare, major version only)

Undeclared impact = rejection.

---

## Versioning Rule (Non-Negotiable)

- Any change that alters admissible states or transitions is **breaking**
- Breaking changes require a **major version bump**
- Minor and patch versions may not change semantics

Tooling adapts. The runtime does not.

---

## Submission Rules

- One concept per pull request
- No bundled changes
- No speculative features
- No future-facing placeholders

ASX-R is conservative by design.

---

## Final Principle

> **ASX-R is a language of law, not code.  
> Precision beats flexibility.**

If in doubt: **do not submit**.
