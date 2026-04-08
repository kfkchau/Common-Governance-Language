## 🧠 Universal Resource Schema – Classification Logic

**Alias**: `RS`  
**Formal Name**: Universal Resource Schema – Classification Logic  

---

### 1. 🧩 Purpose

To classify resources based on their consumability and physicality. This schema enables consistent tagging of entities used in activities, enforcement, and system flows—whether physical, digital, tangible, or abstract.

---

### 2. 🧠 Core Dimensions
| **Dimension**     | **Definition**                          | **Tag Options** |
|-------------------|------------------------------------------|-----------------|
| **Consumability** | Whether the resource is depleted after use | `CO`, `NC` |
| **Physicality**   | Whether the resource has tangible form     | `PH`, `VI` |

---

### 3. 📚 Definitions

- **CO** (Consumable): Resource is used up or transformed after use (e.g. water, fuel, human attention)
- **NC** (Non-Consumable): Resource retains utility after use (e.g. software license, identity)
- **PH** (Physical): Tangible resource (e.g. printed book, hardware)
- **VI** (Virtual): Intangible or digital resource (e.g. digital identity, trust, impressions)

---

### 4. 🧪 Examples

| **Resource**         | **Consumability** | **Physicality** | **Notes** |
|----------------------|-------------------|------------------|-----------|
| Water                | `CO`              | `PH`             | Used up when consumed |
| Software License     | `NC`              | `VI`             | Persistent digital permission |
| Human Attention      | `CO`              | `VI`             | Depletes with use, intangible |
| Printed Document     | `NC`              | `PH`             | Reusable physical item |
| Trust                | `NC`              | `VI`             | Virtual, non-consumable social resource |

---

### 5. 🔗 Integration Points

| **Framework** | **Integration Type** | **Connection** |
|---------------|----------------------|----------------|
| Universal Activity Schema – Directional Logic | Object/Target Typing | Resources used as objects and targets in activities |
| Universal Action Schema – Behavioral Tagging Logic | Action Impact | Actions may consume or transform resources |
| Universal Enforcement Schema – Conditional Outcome Logic | Enforcement Target | Enforcement applies to specific resource types |
| Universal Measurement Schema – Quantification Logic | Resource Metrics | Resources can be tagged with Length, Width, Height |
| Universal Part Schema – Composition Logic | Substructure Typing | RS tags can be applied to parts of a resource |
| Universal Relational Geometry – Spatial Logic | Spatial Typing | Resources can be spatially positioned or scoped |

Temporal state of resources is tracked via their role in activities, which include start and end metadata. This allows resource entities to inherit temporal logic without duplicating it.

---

### 6. 🧭 Visual Schema (Described)

- **Classification Matrix**: 2×2 grid showing Consumability × Physicality
- **Grey Zone Table**: Clarifies ambiguous cases (e.g. software, rights, impressions)
- **Resource Cards**: Each resource tagged with CO/NC and PH/VI

---

### 7. 🕓 Update History

- Created during initial ingestion phase
- Refined with grey zone logic and edge case resolution
- Standardized under coremd-plan format
- Integrated with activity, enforcement, and measurement frameworks

---

### 8. 🏷️ Tags / Typing

| **Tag** | **Meaning** |
|---------|-------------|
| `CO`    | Consumable |
| `NC`    | Non-Consumable |
| `PH`    | Physical |
| `VI`    | Virtual |

---

© Kelvin Chau, 2025  
This work is part of the [Logic Atlas Framework](https://github.com/kfkchau/logic-atlas/).  
For attribution, citation, or inquiries, please refer to:  
🔗 [https://au.linkedin.com/in/kfkchau](https://au.linkedin.com/in/kfkchau)
