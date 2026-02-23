# SUBIT JSON Schema  
*Normative Machine‑Readable Specification for SUBIT States*  
Version 2.0

This document defines the **canonical JSON schema** for representing SUBIT states in machine‑readable form.

The schema is **normative** and part of **SUBIT RFC 2.0**.  
It describes only the structural representation of a SUBIT state.  
Naming systems, archetype tables, and domain‑specific mappings are **not part of this schema**.

---

# 1. Overview

A SUBIT state is a **6‑bit structural configuration**:

```
SUBIT = {0,1}^6
```

The JSON schema defines:

- the 6 axis values  
- the canonical binary representation  
- optional isomorphic encodings (bigram, trigram, color, SVP)  

All fields except the six axes and the binary string are optional.

---

# 2. Canonical Fields

A valid SUBIT state MUST include:

- `tension` (0 or 1)  
- `vector` (0 or 1)  
- `interaction` (0 or 1)  
- `meaning` (0 or 1)  
- `action` (0 or 1)  
- `structure` (0 or 1)  
- `binary` (string of 6 characters, each "0" or "1")  

The `binary` field MUST match the axis values in order:

```
binary = tension + vector + interaction + meaning + action + structure
```

---

# 3. Optional Fields

Implementations MAY include:

- `bigram` — array of three 2‑bit strings  
- `trigram` — array of two 3‑bit strings  
- `color` — array of two color identifiers  
- `svp` — object with `subject`, `vector`, `phase` fields  
- `metadata` — arbitrary implementation‑specific information  

These fields MUST NOT alter the canonical 6‑bit definition.

---

# 4. SUBIT JSON Schema (Canonical)

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "title": "SUBIT State",
  "description": "Canonical machine-readable representation of a SUBIT structural state.",
  "type": "object",
  "properties": {
    "tension": {
      "type": "integer",
      "enum": [0, 1],
      "description": "Axis 1: Tension (0 = Yin, 1 = Yang)"
    },
    "vector": {
      "type": "integer",
      "enum": [0, 1],
      "description": "Axis 2: Vector (0 = Yin, 1 = Yang)"
    },
    "interaction": {
      "type": "integer",
      "enum": [0, 1],
      "description": "Axis 3: Interaction (0 = Yin, 1 = Yang)"
    },
    "meaning": {
      "type": "integer",
      "enum": [0, 1],
      "description": "Axis 4: Meaning (0 = Yin, 1 = Yang)"
    },
    "action": {
      "type": "integer",
      "enum": [0, 1],
      "description": "Axis 5: Action (0 = Yin, 1 = Yang)"
    },
    "structure": {
      "type": "integer",
      "enum": [0, 1],
      "description": "Axis 6: Structure (0 = Yin, 1 = Yang)"
    },
    "binary": {
      "type": "string",
      "pattern": "^[01]{6}$",
      "description": "Canonical 6-bit representation (b1 b2 b3 b4 b5 b6)."
    },
    "bigram": {
      "type": "array",
      "items": {
        "type": "string",
        "pattern": "^[01]{2}$"
      },
      "minItems": 3,
      "maxItems": 3,
      "description": "Optional: three 2-bit bigrams."
    },
    "trigram": {
      "type": "array",
      "items": {
        "type": "string",
        "pattern": "^[01]{3}$"
      },
      "minItems": 2,
      "maxItems": 2,
      "description": "Optional: two 3-bit trigrams."
    },
    "color": {
      "type": "array",
      "items": { "type": "string" },
      "minItems": 2,
      "maxItems": 2,
      "description": "Optional: two-color encoding (implementation-defined palette)."
    },
    "svp": {
      "type": "object",
      "properties": {
        "subject": { "type": "string" },
        "vector": { "type": "string" },
        "phase": { "type": "string" }
      },
      "required": ["subject", "vector", "phase"],
      "description": "Optional: Subject–Vector–Phase encoding."
    },
    "metadata": {
      "type": "object",
      "description": "Optional implementation-specific metadata."
    }
  },
  "required": [
    "tension",
    "vector",
    "interaction",
    "meaning",
    "action",
    "structure",
    "binary"
  ]
}
```

---

# 5. Validation Rules

A SUBIT state is valid if:

1. All six axes are present and are either 0 or 1.  
2. The `binary` field is exactly 6 characters long.  
3. The `binary` field matches the axis values in order.  
4. Optional encodings (bigram, trigram, color, svp) are consistent with the binary value.  
5. No additional fields alter the canonical 6‑bit definition.

---

# 6. Serialization Guidelines

### 6.1 Minimal Serialization (recommended)
```json
{
  "tension": 0,
  "vector": 1,
  "interaction": 0,
  "meaning": 1,
  "action": 1,
  "structure": 0,
  "binary": "010110"
}
```

### 6.2 Extended Serialization (optional)
```json
{
  "tension": 0,
  "vector": 1,
  "interaction": 0,
  "meaning": 1,
  "action": 1,
  "structure": 0,
  "binary": "010110",
  "bigram": ["01", "01", "10"],
  "trigram": ["010", "110"],
  "color": ["Green", "Orange"],
  "svp": {
    "subject": "ME",
    "vector": "WEST",
    "phase": "AUTUMN"
  }
}
```

---

# 7. Notes

- This schema defines **structure**, not semantics.  
- Naming systems and archetype tables are **external** to this schema.  
- Implementations MAY extend metadata but MUST NOT alter the canonical fields.  

---
