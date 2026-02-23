# SUBIT‑64 — Structural Bit Protocol  

SUBIT‑64 is a **formal structural protocol** based on a 6‑bit operator that models any process as a progression through:

**Tension → Vector → Interaction → Meaning → Action → Structure**

SUBIT defines a minimal, deterministic, model‑agnostic operator for structural reasoning in LLMs and agentic systems.

This repository contains:

- SUBIT RFC 2.0 (protocol only)  
- Style‑A reference naming system (separate from RFC)  
- JSON schema for SUBIT states  
- architecture and encoding documentation  
- prompt pack for LLMs  
- examples and integration guides  

SUBIT is not symbolic or metaphorical.  
It is a **structural ontology and reasoning protocol**.

---

## 🔧 Core Idea

A SUBIT state is defined as:

```
SUBIT = {0,1}^6
```

Each bit corresponds to one axis:

1. Tension  
2. Vector  
3. Interaction  
4. Meaning  
5. Action  
6. Structure  

This yields a **64‑state structural space**.  
The RFC defines the operator; implementations may define naming systems or archetype tables.

---

## 📘 Documentation

### **SUBIT RFC 2.0 (Protocol Only)**  
Defines the operator, axes, encoding formats, and mandatory LLM response structure.  
`/docs/SUBIT-RFC.md`

### **Architecture**  
Bit structure, axis semantics, and isomorphic encodings (binary, bigram, trigram, color, SVP).  
`/docs/SUBIT-Architecture.md`

### **JSON Schema**  
Machine‑readable definition of a SUBIT state.  
`/schema/subit.schema.json`

### **Prompt Pack v2.0**  
Operational prompts for LLMs using the SUBIT protocol.  
`/docs/SUBIT-Prompt-Pack-v2.md`

---

## 🧠 SUBIT Response Format (LLM Protocol)

Any LLM operating in SUBIT mode **must** respond using:

```
Tension:
Vector:
Interaction:
Meaning:
Action:
Structure:
```

Rules:

- All six axes must be present  
- Order is fixed  
- No additional sections allowed  

This is the **mandatory protocol** defined by RFC 2.0.

---

## 📂 Repository Structure

```
subit-64/
│
├── README.md
├── LICENSE
├── CHANGELOG.md
├── ROADMAP.md
│
├── docs/
│   ├── SUBIT-RFC.md
│   ├── SUBIT-Architecture.md
│   ├── SUBIT-Prompt-Pack-v2.md
│   └── SUBIT-JSON-Schema.md
│
├── schema/
│   └── subit.schema.json
│
├── examples/
│   ├── subit-analysis.md
│   ├── subit-dialogues.md
│   └── subit-transformations.md
│
└── assets/
    ├── diagrams/
    └── colors/
```

---

## 🚀 Usage

### **In LLMs**
```
Activate SUBIT mode.
Respond in Tension / Vector / Interaction / Meaning / Action / Structure format.
```

### **In agent systems**
- treat SUBIT as a 6‑axis structural operator  
- optionally map states to Style‑A names  
- serialize using the JSON schema  

### **In custom models**
- SUBIT can serve as a reasoning layer  
- or as a structural protocol for analysis/generation  

---

## 🗺️ Roadmap

- SUBIT embeddings  
- transition matrices  
- agent integration standard  
- SUBIT Playground  
- domain‑specific state sets  

---

## 📄 License

MIT

---

## ⭐ Project Goal

To establish SUBIT as a **universal structural protocol** for LLM reasoning, agentic systems, and computational cognition.
```

---
