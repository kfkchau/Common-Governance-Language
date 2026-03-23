## 🧠 Universal Part Schema – Composition Logic

**Alias**: `part01`  
**Formal Name**: Universal Part Schema – Composition Logic  

---

### 1. 🧩 Purpose

To classify all possible ways a resource—or part of a resource—can be scoped, described, or referenced. This schema enables precise modeling of partial relationships, targeted actions, and spatial logic when combined with frameworks like Venn2, RS, and AC.

---

### 2. 🧠 Core Dimensions

Grouped into three conceptual pairs:

| **Group**              | **Dimension** | **Definition** |
|------------------------|---------------|----------------|
| **Structural Scope**   | `whole`       | The entire entity |
|                        | `component`   | A specific part or sub-unit |
| **Boundary Logic**     | `surface`     | The outermost layer or boundary |
|                        | `inside`      | Everything excluding the surface |
| **Structural Composition** | `wireframe`   | The internal frame or skeleton |
|                        | `content`     | Everything excluding the wireframe, including surface |

---

### 3. 📚 Definitions

| **Category** | **Definition** | **Example (Human Body)** |
|--------------|----------------|---------------------------|
| `whole`      | Entire entity | The whole human body |
| `component`  | Sub-unit | The heart, the head |
| `surface`    | Outer boundary | Skin |
| `inside`     | Internal volume | Organs, bones, blood |
| `wireframe`  | Structural frame | Skeleton |
| `content`    | Non-frame material | Organs, tissues, skin |

---

### 4. 🧪 Examples

| **Domain**     | **Use Case**                        | **Part01 Application** |
|----------------|-------------------------------------|-------------------------|
| Medical        | “Apply bandage to skin”             | `surface` ∩ `component:arm` |
| Engineering    | “Inspect internal wiring”           | `inside` ∩ `wireframe` |
| Digital        | “Encrypt header of packet”          | `component` ∩ `surface` |
| Policy         | “Regulation applies to outer casing only” | `surface` |
| Logistics      | “Label must be visible on all sides”| `surface` ∪ `component:sides` |

---

### 5. 🔗 Integration Points

| **Framework** | **Integration Type** | **Connection** |
|---------------|----------------------|----------------|
| Universal Activity Schema – Directional Logic | Target/Object Scoping | Activities can target specific parts of a resource |
| Universal Resource Schema – Classification Logic | Substructure Typing | RS tags can be applied to parts of a resource |
| Universal Relational Geometry – Spatial Logic | Spatial Composition | Parts are positioned using Venn2 spatial logic |
| Universal Measurement Schema – Quantification Logic | Part Metrics | Parts can be measured (e.g. surface area, internal volume) |
| Universal Enforcement Schema – Conditional Outcome Logic | Targeted Enforcement | Enforcement can apply to specific parts (e.g. protect surface) |

---

### 6. 🧭 Visual Schema (Described)

- **Whole**: Full circle
- **Component**: Labeled segment or sub-circle
- **Surface**: Thin outer ring
- **Inside**: Area inside the ring
- **Wireframe**: Skeletal structure inside the circle
- **Content**: Filled area excluding wireframe

Can be combined with Venn2 overlays to model spatial relationships (e.g. `component` ∩ `inside` ∩ `embedded` = “Heart inside body”).

---

### 7. 🕓 Update History

- Created during ingestion of PR-PTnCore3 1.docx
- Expanded with grouping logic and examples
- Standardized under coremd-plan format
- Integrated with spatial, activity, and enforcement frameworks

---

### 8. 🏷️ Tags / Typing

| **Tag**      | **Meaning** |
|--------------|-------------|
| `whole`      | Entire entity |
| `component`  | Sub-unit |
| `surface`    | Outer boundary |
| `inside`     | Internal volume |
| `wireframe`  | Structural frame |
| `content`    | Non-frame material |

---

© Kelvin Chau, 2025  
This work is part of the [Logic Atlas Framework](https://github.com/kfkchau/logic-atlas/).  
For attribution, citation, or inquiries, please refer to:  
🔗 [https://au.linkedin.com/in/kfkchau](https://au.linkedin.com/in/kfkchau)
