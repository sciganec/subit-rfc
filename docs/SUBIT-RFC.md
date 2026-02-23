# SUBIT RFC 2.0 — Structural Bit Protocol  

## Status of This Memo
This document defines **SUBIT RFC 2.0**, the formal specification of the SUBIT Structural Bit Protocol.

This RFC describes **only the protocol**:  
- the 6‑axis operator  
- the 6‑bit encoding  
- axis semantics  
- required LLM response format  
- allowed isomorphic representations  
- the normative JSON schema  

Concrete implementations (e.g., naming systems, archetype tables, domain‑specific mappings) are **not part of this RFC** and MUST be defined in separate documents.

---

# 1. Introduction

**SUBIT** is a six‑axis structural operator that models any process as a progression through:

**Tension → Vector → Interaction → Meaning → Action → Structure**

A SUBIT state is represented as a **6‑bit configuration**, where each bit corresponds to one structural axis.

SUBIT is:

- minimal  
- deterministic  
- model‑agnostic  
- extensible  
- suitable for LLM reasoning and agentic systems  

This RFC defines the operator, its encoding, and the mandatory response protocol.

---

# 2. SUBIT Definition

A SUBIT state is defined as:

```
SUBIT = {0,1}^6
```

This yields a structural state space of:

```
2^6 = 64 possible configurations
```

Implementations MAY define naming systems or state tables, but these are **not normative** and MUST NOT modify the protocol.

---

# 3. Axis Definitions

Each bit corresponds to one axis:

### 3.1 Tension (b1)  
Unresolved force, ambiguity, or initiating pressure.

### 3.2 Vector (b2)  
Directional intention or movement.

### 3.3 Interaction (b3)  
Relational dynamics between elements or agents.

### 3.4 Meaning (b4)  
Interpretation, pattern, or significance.

### 3.5 Action (b5)  
Transformation, event, or operative step.

### 3.6 Structure (b6)  
Resulting configuration or stabilized form.

Each axis has two polarities:

- **0 = Yin** (latent, receptive, passive)  
- **1 = Yang** (active, directed, manifest)

---

# 4. Encoding Formats

SUBIT supports multiple isomorphic representations.

## 4.1 Binary (canonical)
```
b1 b2 b3 b4 b5 b6
```

## 4.2 Bigram Encoding (3 × 2‑bit)
```
(00, 01, 10, 11)^3
```

## 4.3 Trigram Encoding (2 × 3‑bit)
Two trigrams from the canonical 8‑trigram set:
```
000–111
```

## 4.4 Color Encoding (2‑color pair)
Implementations MAY define an 8‑color palette.

## 4.5 Subject–Vector–Phase Encoding (4×4×4)
Implementations MAY define a 4×4×4 mapping.

These representations are **optional** and MUST NOT alter the canonical 6‑bit definition.

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

1. All six axes MUST be present.  
2. Order MUST be preserved.  
3. No additional sections MAY be inserted.  
4. Content MAY be short or extended.  
5. Axis semantics MUST NOT be altered.  

This is the **mandatory protocol**.

---

# 6. Machine‑Readable Schema

The SUBIT schema defines the structure of a SUBIT state.

Implementations MUST provide:

- a 6‑bit binary representation  
- axis values (0/1)  
- optional isomorphic encodings  

The canonical JSON schema is provided in:

```
/schema/subit.schema.json
```

This schema is normative.

---

# 7. Implementation Notes

- SUBIT is deterministic: same input → same structural decomposition.  
- SUBIT MAY be used as a reasoning layer in LLMs.  
- SUBIT MAY be used as a state machine in agent systems.  
- Implementations MAY define naming systems, state tables, or extended state sets.  
- Such implementations MUST NOT modify the protocol defined in this RFC.  
- Implementations MAY serialize SUBIT states using the JSON schema.  

---

# 8. Versioning

This document defines:

**SUBIT RFC 2.0 — Structural Bit Protocol**

Future versions MAY include:

- extended operators  
- transition matrices  
- multi‑layer SUBIT stacks  
- domain‑specific extensions  

State tables and naming systems are versioned separately.

---

