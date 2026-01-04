# What ASX-R *is* 

**ASX-R is not:**

* an app framework
* a reference implementation
* a JS / WASM project
* a collection of utilities

**ASX-R *is*:**

> **A runtime language whose execution is defined by admissible state, not by code.**

So the GitHub repo must feel more like:

* a **language definition**
* a **runtime contract**
* a **lawbook**
  than like a software package.

Think **WebAssembly spec**, **Ethereum Yellow Paper**, **JSON Schema**, **CSS spec** — not npm.

---

# The core mistake to avoid

❌ Don’t organize it around:

* tools
* demos
* interpreters
* bindings
* builds

Those come later and live **outside** ASX-R.

✅ Organize it around:

* **what exists**
* **what is allowed**
* **how time progresses**
* **how projection works**
* **what may never happen**

That’s the runtime.

---

# Canonical ASX-R GitHub structure (clean + future-proof)

Here is the structure I strongly recommend locking in:

```
ASX-R/
├── README.md
├── ASX-R_SPEC.md
├── RUNTIME_LAWS.md
├── CHANGELOG.md
├── LICENSE
│
├── schemas/
│   ├── core/
│   │   ├── asx-r.schema.json
│   │   ├── xjson.schema.json
│   │   ├── atomic-block.schema.json
│   │   ├── atomic-css.schema.json
│   │   └── scxq2.schema.json
│   │
│   ├── runtime/
│   │   ├── phase.schema.json
│   │   ├── transition.schema.json
│   │   ├── epoch.schema.json
│   │   └── proof.schema.json
│   │
│   └── projection/
│       ├── dom.schema.json
│       ├── gpu.schema.json
│       ├── mesh.schema.json
│       └── io.schema.json
│
├── laws/
│   ├── json-runtime-axiom.md
│   ├── interpreter-non-authority.md
│   ├── projection-law.md
│   ├── compression-as-execution.md
│   └── determinism-and-replay.md
│
├── atomic/
│   ├── atomic-blocks.md
│   ├── atomic-css.md
│   ├── atomic-css-runtime.md
│   └── examples/
│       ├── ui.json
│       ├── world.json
│       └── agent.json
│
├── runtime/
│   ├── phases.md
│   ├── ticks.md
│   ├── barriers.md
│   └── collapse.md
│
├── conformance/
│   ├── rules.md
│   ├── invalid-states/
│   ├── valid-states/
│   └── replay-vectors/
│
└── projections/
    ├── dom.md
    ├── css.md
    ├── svg.md
    ├── gpu.md
    └── mesh.md
```

This repo **contains no executable code by default** — and that is a *feature*, not a weakness.

---

# What each top-level file does (important)

### `README.md`

High-level declaration:

* ASX-R is a **runtime language**
* JSON is the **surface syntax**
* Execution = **state admissibility**
* Code is a **projection engine**

This sets expectations immediately.

---

### `ASX-R_SPEC.md`

This is the **single canonical document** that answers:

* What is ASX-R?
* What is a state?
* What is a transition?
* What is time?
* What is execution?
* What is forbidden?

This is your “language spec”.

---

### `RUNTIME_LAWS.md`

Short, sharp, non-negotiable rules:

* closed world
* no hidden state
* no side effects
* no undefined behavior
* replay sufficiency

This is what prevents future drift.

---

# Why Atomic Blocks + Atomic CSS belong *inside* ASX-R

This is important, and you’re right about it.

Atomic Blocks and Atomic CSS are **not UI frameworks** in your system.

They are:

> **First-class state languages inside the runtime**

Which means:

* Atomic Blocks define **structural existence**
* Atomic CSS defines **projection state**, not styling logic

They are runtime primitives, not add-ons.

That’s why they live in:

```
/atomic/
```

not `/examples/` or `/tools/`.

---

# What does *not* go in this repo (by design)

❌ No JS runtime
❌ No service worker
❌ No DOM renderer
❌ No GPU engine
❌ No CLI
❌ No build scripts

Those belong in:

* `asx-js-runtime`
* `asx-wasm-runtime`
* `asx-dom-projector`
* `asx-gpu-projector`

ASX-R itself stays **pure**.

---

# The key framing sentence for GitHub

I recommend putting this near the top of the README:

> **ASX-R is a runtime language.
> Implementations execute it; they do not define it.**

That one line will save you years of argument.

---
