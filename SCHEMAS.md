Below are the **canonical, minimal JSON Schemas** for **Atomic Blocks** and **Atomic CSS Projection State**, written to be **normative, closed, and verifier-friendly**.

They are intentionally **minimal**: everything else composes on top without weakening law.

Paste verbatim as the indicated files.

---

## `schemas/core/atomic-block.schema.json`

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "asx://schema/atomic-block.v1",
  "title": "ASX-R Atomic Block Schema",
  "type": "object",
  "required": ["@id", "@type", "role"],
  "additionalProperties": false,

  "properties": {
    "@id": {
      "type": "string",
      "description": "Stable, explicit identity of the atomic block"
    },

    "@type": {
      "type": "string",
      "description": "Declared atomic block type (closed set by runtime/schema)"
    },

    "role": {
      "type": "string",
      "description": "Structural role of the block (semantic, non-behavioral)"
    },

    "children": {
      "type": "array",
      "description": "Explicit containment of child atomic blocks",
      "items": {
        "$ref": "asx://schema/atomic-block.v1"
      },
      "uniqueItems": true
    },

    "adjacent": {
      "type": "array",
      "description": "Explicit adjacency references (composition without containment)",
      "items": {
        "type": "string"
      },
      "uniqueItems": true
    },

    "meta": {
      "type": "object",
      "description": "Optional structural metadata (non-behavioral)",
      "additionalProperties": true
    }
  }
}
```

### Normative Notes (Atomic Blocks)

* `@id` **MUST** be explicit and stable
* `children` defines **containment** (acyclic, enforced by invariant)
* `adjacent` defines **composition**, not hierarchy
* No behavior, logic, or transitions are permitted
* `additionalProperties: false` enforces **closed structure**

---

## `schemas/core/atomic-css.schema.json`

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "asx://schema/atomic-css.v1",
  "title": "ASX-R Atomic CSS Projection Schema",
  "type": "object",
  "required": ["target", "classes", "vars"],
  "additionalProperties": false,

  "properties": {
    "target": {
      "type": "string",
      "description": "Atomic Block @id this projection applies to"
    },

    "classes": {
      "type": "array",
      "description": "Semantic atomic classes applied to the target",
      "items": {
        "type": "string"
      },
      "uniqueItems": true
    },

    "vars": {
      "type": "object",
      "description": "Projection variables reflecting runtime state",
      "additionalProperties": {
        "type": ["string", "number", "boolean"]
      }
    },

    "phase": {
      "type": "string",
      "description": "Optional runtime phase this projection reflects"
    }
  }
}
```

### Normative Notes (Atomic CSS)

* Atomic CSS **only references** runtime state (`target`, `phase`)
* `vars` are **read-only projections**, not logic
* No structural mutation is possible
* No control flow or behavior encoding is permitted
* Closed schema prevents hidden authority

---

## Relationship Constraint (Normative)

These schemas are **orthogonal but bound**:

* Every `atomic-css.target` **MUST** reference a valid Atomic Block `@id`
* Atomic CSS **cannot create** blocks
* Atomic Blocks **do not depend** on Atomic CSS for validity

This relationship is enforced by **conformance rules**, not schema recursion.

---

## Why these schemas are minimal (by design)

* They define **existence**, not convenience
* They are verifier-first, not developer-first
* They prevent authority leakage
* They compose cleanly with SCXQ2, phases, epochs, and projection engines

Everything else (themes, UI kits, animations, layouts) is **derived**, not baked in.

---

### ✅ JSON Schemas — LOCKED

You now have:

* Runtime laws
* Foundational axiom
* Atomic Block language
* Atomic CSS runtime
* Conformance + invalid state catalog
* **Authoritative schemas**
