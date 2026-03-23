## 🧠 Universal Relational Geometry – Spatial Logic

**Alias**: `Venn2`  
**Formal Name**: Universal Relational Geometry – Spatial Logic  

---

### 1. 🧩 Purpose

To classify spatial relationships between entities using five mutually exclusive categories. This schema enables bottom-up relational mapping across physical, digital, and conceptual domains, replacing absolute reference models with relational geometry.

---

### 2. 🧠 Core Dimensions

| **Category**   | **Definition**                              | **Visual Metaphor** |
|----------------|----------------------------------------------|---------------------|
| **Unrelated**  | Entities have a measurable spatial gap       | ○ ○                 |
| **Adjacent**   | Entities touch at boundary                   | ○●                 |
| **Intersecting**| Entities share partial volume               | ◐                  |
| **Nested**     | One entity fully enclosed, touching boundary | ◉                  |
| **Embedded**   | One entity fully enclosed, not touching boundary | ◎              |

---

### 3. 📚 Definitions

- **Unrelated**: No contact or enclosure
- **Adjacent**: Surface contact only
- **Intersecting**: Partial volume overlap
- **Nested**: Full enclosure with boundary contact
- **Embedded**: Full enclosure without boundary contact

---

### 4. 🧪 Examples

| **Scenario** | **Entity A** | **Entity B** | **Relationship** |
|--------------|--------------|--------------|------------------|
| Coke inside fridge | Coke | Fridge | Embedded |
| John holding Coke | John | Coke | Adjacent |
| Two overlapping zones | Zone A | Zone B | Intersecting |
| Ball in bowl | Ball | Bowl | Nested |
| Person near fridge | Person | Fridge | Unrelated |

Test case sequence:  
> T0: Coke & Fridge = Embedded  
> T1: John opens fridge → Coke becomes Nested  
> T2: John holds Coke → Coke & John = Adjacent  
> T3: Coke removed → Coke & Fridge = Unrelated

---

### 5. 🔗 Integration Points

| **Framework** | **Integration Type** | **Connection** |
|---------------|----------------------|----------------|
| Universal Activity Schema – Directional Logic | Spatial Context | Activities scoped spatially |
| Universal Resource Schema – Classification Logic | Spatial Typing | Resources classified by spatial position |
| Universal Part Schema – Composition Logic | Spatial Composition | Parts positioned using Venn2 logic |
| Universal Relationship Schema – Architecture Logic | Overlay Logic | Venn2 overlays ST architecture spatially |
| Universal Conditional Logic – Precondition Logic | Spatial Constraint | Spatial relationships act as preconditions for activity links |

---

### 6. 🧭 Visual Schema (Described)

- **Nodes**: Entities represented as circles
- **Edges**: Spatial relationships shown by overlap, containment, or adjacency
- **Transitions**: Arrows showing movement between states (e.g. Adjacent → Intersecting → Nested)
- **Metadata**: Each relationship can carry temporal attributes (duration, volatility, directionality)

---

### 7. 🕓 Update History

- Created during early ingestion phase
- Refined with spatial schema and test cases
- Expanded to support temporal transitions and metadata tagging
- Standardized under coremd-plan format
- Integrated with part01, act01, EF01, and coremd-logic
---

### 8. 🏷️ Tags / Typing

| **Tag** | **Meaning** |
|---------|-------------|
| `UR`    | Unrelated |
| `AD`    | Adjacent |
| `IN`    | Intersecting |
| `NS`    | Nested |
| `EM`    | Embedded |

---

© Kelvin Chau, 2025  
This work is part of the [Logic Atlas Framework](https://github.com/kfkchau/logic-atlas/).  
For attribution, citation, or inquiries, please refer to:  
🔗 [https://au.linkedin.com/in/kfkchau](https://au.linkedin.com/in/kfkchau)
