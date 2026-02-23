# SUBIT Color Standard v1.1  
*Canonical 8‑Color Trigram Palette (Isomorphism Layer)*  

This document defines the **official color encoding standard** for the SUBIT Structural Bit Protocol, aligned with:

- SUBIT RFC 2.0  
- SUBIT Architecture 2.0  
- SUBIT Isomorphism Standard v1.0  

Color is an **optional isomorphic layer**.  
It does not modify the SUBIT operator.

This version (v1.1) replaces the RGB‑bit palette with the **canonical 8‑color palette** defined in the SUBIT Isomorphism Standard:

```
Blue, Green, Lime, Yellow, Orange, Red, Burgundy, Purple
```

These eight colors correspond **one‑to‑one** with the eight SUBIT trigrams.

---

# 1. Canonical 8‑Color Trigram Palette

Each SUBIT trigram (3‑bit vector) is mapped to one of the eight canonical colors.

| Trigram | Bits | Color Name | Hex |
|--------|------|-------------|------|
| T0 | 000 | Blue | #0066FF |
| T1 | 001 | Green | #00CC66 |
| T2 | 010 | Lime | #66FF33 |
| T3 | 011 | Yellow | #FFCC00 |
| T4 | 100 | Orange | #FF8800 |
| T5 | 101 | Red | #FF0033 |
| T6 | 110 | Burgundy | #660033 |
| T7 | 111 | Purple | #6633CC |

Notes:

- These colors come directly from **Isomorphism Layer 12**.  
- They are **canonical and immutable**.  
- They replace the RGB bit‑mapped palette from v1.0.  
- They preserve the 8‑fold symmetry of the SUBIT trigram set.

---

# 2. SUBIT 64‑Color Matrix  
*Trigram × Trigram → 64 unique colors*

A SUBIT state consists of:

```
upper trigram (3 bits)
lower trigram (3 bits)
```

Each trigram maps to one of the 8 canonical colors.

The canonical color for the full 6‑bit state is computed using **multiply blending**:

```
R = (R_upper * R_lower) / 255
G = (G_upper * G_lower) / 255
B = (B_upper * B_lower) / 255
```

Reasons for multiply:

- deterministic  
- associative  
- preserves SUBIT’s fractal geometry  
- visually stable  
- produces a consistent 64‑color matrix  

---

# 3. JSON Encoding (Optional)

```json
"color": {
  "upper": "Orange",
  "lower": "Blue",
  "blend": "#000000"
}
```

Rules:

- `upper` and `lower` MUST be one of the 8 canonical colors  
- `blend` MUST use the multiply rule  
- No alternative palettes are permitted  

---

# 4. Implementation Rules

1. The 8‑color palette is **fixed** and defined by the Isomorphism Standard.  
2. The mapping trigram → color is **fixed**.  
3. The 64‑color matrix MUST use multiply blending.  
4. Implementations MAY display:  
   - upper color  
   - lower color  
   - blended color  
   - or all three  
5. Colors MUST NOT be reinterpreted symbolically.  
6. Colors MUST NOT be remapped or reordered.  
7. Colors MUST NOT imply meaning beyond structure.

---

# 5. Summary

- SUBIT uses the 8‑color palette from the Isomorphism Standard.  
- Each trigram maps to one canonical color.  
- SUBIT states produce a 64‑color matrix via multiply blending.  
- Color is an optional isomorphic layer.  
- This standard ensures visual consistency across all SUBIT implementations.

---
