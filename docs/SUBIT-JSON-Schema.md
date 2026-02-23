# SUBIT JSON Schema Documentation  

This document defines the **official JSON schema** for representing SUBIT states, archetypes, and structural metadata.  
It is intended for use in:

- LLMs  
- agentic systems  
- reasoning engines  
- data pipelines  
- visualization tools  
- SUBIT‑compatible applications  

The schema is model‑agnostic and designed for long‑term stability.

---

# 1. Overview

A **SUBIT state** is a 6‑bit structural configuration:

```
SUBIT = {0,1}^6
```

Each bit corresponds to one of the six axes:

1. Tension  
2. Vector  
3. Interaction  
4. Meaning  
5. Action  
6. Structure  

This yields **64 archetypes**, each of which can be represented in multiple isomorphic formats:

- binary  
- bigram (3×2‑bit)  
- trigram (2×3‑bit)  
- color pair  
- subject–vector–phase triple  

The JSON schema standardizes these representations.

---

# 2. Files

The SUBIT JSON system consists of:

### **2.1. subit.schema.json**  
Defines the structure of a single SUBIT state or archetype.

### **2.2. archetypes.json**  
Contains the full list of 64 archetypes in machine‑readable form.

### **2.3. Supporting files**
- `subit-colors.json`  
- optional per‑archetype files in `/data/archetypes/`

---

# 3. SUBIT Schema (subit.schema.json)

Below is the canonical schema for a SUBIT state.

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "title": "SUBIT State Schema",
  "type": "object",
  "required": ["id", "binary", "bigram", "trigram", "color", "subject", "vector", "phase", "name"],
  "properties": {
    "id": {
      "type": "integer",
      "minimum": 0,
      "maximum": 63,
      "description": "Archetype index (0–63)."
    },
    "binary": {
      "type": "string",
      "pattern": "^[01]{6}$",
      "description": "6-bit binary representation."
    },
    "bigram": {
      "type": "array",
      "items": {
        "type": "string",
        "pattern": "^[01]{2}$"
      },
      "minItems": 3,
      "maxItems": 3,
      "description": "Three 2-bit bigrams."
    },
    "trigram": {
      "type": "array",
      "items": {
        "type": "string",
        "pattern": "^[01]{3}$"
      },
      "minItems": 2,
      "maxItems": 2,
      "description": "Two 3-bit trigrams."
    },
    "color": {
      "type": "array",
      "items": {
        "type": "string",
        "enum": ["Blue", "Green", "Lime", "Yellow", "Orange", "Red", "Burgundy", "Purple"]
      },
      "minItems": 2,
      "maxItems": 2,
      "description": "Color pair representation."
    },
    "subject": {
      "type": "string",
      "enum": ["ME", "WE", "YOU", "THEY"],
      "description": "Subject axis."
    },
    "vector": {
      "type": "string",
      "enum": ["EAST", "SOUTH", "WEST", "NORTH"],
      "description": "Vector axis."
    },
    "phase": {
      "type": "string",
      "enum": ["SPRING", "SUMMER", "AUTUMN", "WINTER"],
      "description": "Phase axis."
    },
    "name": {
      "type": "string",
      "description": "Canonical archetype name."
    },
    "description": {
      "type": "string",
      "description": "Short description of the archetype."
    }
  }
}
```

---

# 4. Archetype Set (archetypes.json)

This file contains an array of **64 objects**, each conforming to the schema above.

Example entry:

```json
{
  "id": 0,
  "binary": "000000",
  "bigram": ["00", "00", "00"],
  "trigram": ["000", "000"],
  "color": ["Blue", "Blue"],
  "subject": "ME",
  "vector": "EAST",
  "phase": "SPRING",
  "name": "Origon",
  "description": "Pure potential, unformed state."
}
```

The full file is located at:

```
/schema/archetypes.json
```

---

# 5. Color Palette (subit-colors.json)

The canonical 8‑color palette:

```json
[
  "Blue",
  "Green",
  "Lime",
  "Yellow",
  "Orange",
  "Red",
  "Burgundy",
  "Purple"
]
```

---

# 6. Validation

Any SUBIT state or archetype can be validated using standard JSON Schema tools:

- `ajv`  
- `jsonschema`  
- `pydantic`  
- `typescript-json-schema`  

Example (Node.js):

```bash
npx ajv validate -s schema/subit.schema.json -d schema/archetypes.json
```

---

# 7. Usage in LLMs and Agents

### **7.1. LLMs**
- load `archetypes.json`  
- use `subit.schema.json` to enforce structure  
- generate or analyze states using the SUBIT protocol  

### **7.2. Agents**
- treat SUBIT as a state machine  
- use archetypes as nodes  
- transitions can be defined externally  

### **7.3. Tools**
- visualization  
- clustering  
- reasoning layers  
- structural embeddings  

---

# 8. Versioning

This document defines:

**SUBIT JSON Schema v1.0**

Future versions may include:

- extended metadata  
- transition maps  
- embedding vectors  
- archetype families  

---
