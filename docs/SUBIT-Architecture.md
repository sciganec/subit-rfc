# SUBIT Architecture  
*Structural Model, Axes, and Encoding Isomorphisms*  
Version 2.0

This document defines the **architectural foundations** of the SUBIT Structural Bit Protocol.  
It describes the six axes, the 6‑bit structure, and the isomorphic encoding layers that can be used to represent SUBIT states.

This document does **not** define archetypes, naming systems, or state tables.  
Those are implementation‑specific and maintained separately.

---

# 1. Overview

SUBIT is a **six‑axis structural operator** that models any process as a progression through:

**Tension → Vector → Interaction → Meaning → Action → Structure**

A SUBIT state is represented as a **6‑bit vector**:

```
SUBIT = {0,1}^6
```

This yields a structural state space of:

```
2^6 = 64 possible configurations
```

SUBIT is:

- minimal  
- deterministic  
- model‑agnostic  
- extensible  
- suitable for LLMs and agentic systems  

---

# 2. The Six Axes

Each bit corresponds to one structural axis.

## 2.1 Tension (b1)
Unresolved force, ambiguity, or initiating pressure.

## 2.2 Vector (b2)
Directional intention or movement.

## 2.3 Interaction (b3)
Relational dynamics between elements or agents.

## 2.4 Meaning (b4)
Interpretation, pattern, or significance.

## 2.5 Action (b5)
Transformation, event, or operative step.

## 2.6 Structure (b6)
Resulting configuration or stabilized form.

### Polarity
Each axis has two polarities:

- **0 = Yin** (latent, receptive, passive)  
- **1 = Yang** (active, directed, manifest)

---

# 3. Canonical Representation

The canonical representation of a SUBIT state is a **6‑bit binary string**:

```
b1 b2 b3 b4 b5 b6
```

Example (not tied to any archetype):

```
010111
```

---

# 4. Isomorphic Encodings

SUBIT supports multiple **isomorphic** (mathematically equivalent) representations.  
These encodings do not change the underlying 6‑bit structure.

Implementations MAY use any of the following.

---

## 4.1 Bigram Encoding (3 × 2‑bit)

The 6 bits can be grouped into three bigrams:

```
(b1 b2), (b3 b4), (b5 b6)
```

Each bigram is one of:

```
00, 01, 10, 11
```

Example:

```
["01", "10", "11"]
```

---

## 4.2 Trigram Encoding (2 × 3‑bit)

The 6 bits can be grouped into two trigrams:

```
(b1 b2 b3), (b4 b5 b6)
```

Each trigram is one of the canonical 8:

```
000
001
010
011
100
101
110
111
```

Example:

```
["010", "111"]
```

---

## 4.3 Color Encoding (2‑Color Pair)

Implementations MAY define an 8‑color palette and map each trigram to a color.

Example palette (non‑normative):

```
Blue, Green, Lime, Yellow, Orange, Red, Burgundy, Purple
```

Example encoding:

```
["Lime", "Red"]
```

---

## 4.4 Subject–Vector–Phase Encoding (4×4×4)

Implementations MAY define a 4×4×4 mapping:

- **Subjects** (4)  
- **Vectors** (4)  
- **Phases** (4)  

Example categories (non‑normative):

```
Subjects: ME, WE, YOU, THEY
Vectors: EAST, SOUTH, WEST, NORTH
Phases: SPRING, SUMMER, AUTUMN, WINTER
```

This encoding is optional and domain‑specific.

---

# 5. Structural Dynamics

SUBIT is not only a static encoding — it is a **process operator**.

A SUBIT response always follows the sequence:

```
Tension:
Vector:
Interaction:
Meaning:
Action:
Structure:
```

This models:

1. **Problem emergence**  
2. **Directional intention**  
3. **Relational dynamics**  
4. **Interpretation**  
5. **Transformation**  
6. **Stabilization**  

This sequence is mandatory for LLMs using the SUBIT protocol.

---

# 6. Architectural Principles

## 6.1 Minimality
SUBIT uses the smallest possible structure (6 bits) that still captures:

- tension  
- direction  
- relationality  
- interpretation  
- transformation  
- form  

## 6.2 Determinism
Given the same input, SUBIT produces the same structural decomposition.

## 6.3 Isomorphism
All encodings (binary, bigram, trigram, color, SVP) are equivalent views of the same structure.

## 6.4 Extensibility
Implementations MAY define:

- naming systems  
- archetype tables  
- extended state sets  
- domain‑specific mappings  

These MUST NOT modify the protocol.

---

