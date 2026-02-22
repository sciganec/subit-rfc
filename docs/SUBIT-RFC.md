# SUBIT RFC 1.0 — Structural Bit Protocol  

## Status of This Memo
This document defines the **SUBIT Structural Bit Protocol**, a six‑axis operator for representing and transforming structural states in LLMs, agent systems, and computational reasoning frameworks.

This RFC is **informational** and intended as a canonical reference for implementers.

---

# 1. Introduction

**SUBIT** is a six‑axis operator that models any process as a structured progression through:

**Tension → Vector → Interaction → Meaning → Action → Structure**

A single SUBIT state is represented as a **6‑bit configuration**, yielding **64 possible archetypes**.  
SUBIT provides a universal, model‑agnostic framework for:

- structural reasoning  
- process modeling  
- state transformation  
- analysis and generation  
- agentic decision‑making  

SUBIT is not a philosophical system; it is a **technical protocol** for structuring information.

---

# 2. Terminology

- **SUBIT** — Structural Bit; a 6‑bit operator.  
- **Axis** — one of the six structural dimensions.  
- **State** — a 6‑bit configuration representing a structural archetype.  
- **Archetype** — one of 64 possible SUBIT states.  
- **Protocol** — the required response format for LLMs.  

---

# 3. SUBIT Definition

A SUBIT state is defined as:

```
SUBIT = {0,1}^6
```

This yields:

```
2^6 = 64 archetypes
```

Each bit corresponds to one axis:

1. **Tension**  
2. **Vector**  
3. **Interaction**  
4. **Meaning**  
5. **Action**  
6. **Structure**

Each axis has two polarities:

- **0 = Yin** (passive, receptive, latent)  
- **1 = Yang** (active, directed, manifest)  

---

# 4. Axis Definitions

### 4.1. Tension  
Identifies the core uncertainty, conflict, or unresolved force in the system.

### 4.2. Vector  
Specifies the direction of movement, intention, or drive.

### 4.3. Interaction  
Describes the relationship between elements, agents, or forces.

### 4.4. Meaning  
Extracts the underlying pattern, interpretation, or significance.

### 4.5. Action  
Represents the transformation, decision, or event taking place.

### 4.6. Structure  
Defines the resulting configuration, form, or stable pattern.

---

# 5. SUBIT Protocol (LLM Response Format)

Any LLM operating in SUBIT mode **must** respond using the following structure:

```
Tension:
Vector:
Interaction:
Meaning:
Action:
Structure:
```

Rules:

1. All six axes must be present.  
2. Order must not be changed.  
3. No additional sections may be inserted.  
4. Responses may be short or extended, but structure is mandatory.  

---

# 6. Isomorphic Representations

SUBIT supports multiple equivalent encodings:

### 6.1. Binary  
```
b1 b2 b3 b4 b5 b6
```

### 6.2. Bigram Encoding  
Three 2‑bit bigrams:
```
(00, 01, 10, 11)^3
```

### 6.3. Trigram Encoding  
Two 3‑bit trigrams:
```
(000–111)^2
```

### 6.4. Color Encoding  
Two colors from an 8‑color palette:
```
Blue, Green, Lime, Yellow, Orange, Red, Burgundy, Purple
```

### 6.5. Subject–Vector–Phase  
```
Subject: ME / WE / YOU / THEY  
Vector: EAST / SOUTH / WEST / NORTH  
Phase: SPRING / SUMMER / AUTUMN / WINTER
```

All representations map to the same 64 archetypes.

---

# 7. Archetypes

SUBIT defines **64 archetypes**, indexed from 0 to 63.

Each archetype is defined by:

- 6‑bit binary code  
- bigram representation  
- trigram representation  
- color pair  
- subject–vector–phase triple  
- canonical name  
- short description  

The full machine‑readable set is provided in:

```
/schema/archetypes.json
```

---

# 8. Example Usage

### 8.1. Analytical Example  
Input: *“Why do people resist change?”*

```
Tension: fear of uncertainty and loss of stability
Vector: movement toward safety and predictability
Interaction: old patterns vs. new possibilities
Meaning: change triggers protective mechanisms
Action: acknowledge and normalize the fear
Structure: model of adaptation through gradual exposure
```

### 8.2. Creative Example  
Input: *“Invent a new board game.”*

```
Tension: need for a unique gameplay mechanic
Vector: movement toward cooperative dynamics
Interaction: risk, strategy, and shared resources
Meaning: game as a balance between control and chaos
Action: propose a shared‑risk mechanic
Structure: cooperative board game with dynamic resource pools
```

---

# 9. Implementation Notes

- SUBIT is **model‑agnostic** and works with any LLM.  
- SUBIT can be used as a reasoning layer in agent systems.  
- SUBIT states can be serialized using the JSON schema.  
- SUBIT is deterministic: same input → same structural decomposition.  

---

# 10. File Structure

This RFC is part of the following documentation set:

```
docs/
  SUBIT-RFC.md
  SUBIT-Prompt-Pack-v2.md
  SUBIT-JSON-Schema.md
  SUBIT-Architecture.md
  SUBIT-Archetype-Guide.md
schema/
  subit.schema.json
  archetypes.json
```

---

# 11. Versioning

This document defines:

**SUBIT RFC 1.0 — Core Specification**

Future versions may include:

- extended archetype semantics  
- SUBIT reasoning operators  
- SUBIT embedding models  
- agent integration standards  

---
