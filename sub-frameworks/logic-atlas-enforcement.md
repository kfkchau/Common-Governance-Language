## 🧠 Universal Connection Logic – Activity Linkage Framework

**Alias**: `coremd-logic`  
**Formal Name**: Universal Connection Logic – Activity Linkage Framework  

---

### 1. 🧩 Purpose

To define how activities are conditionally linked using structural, logical, and temporal rules. This schema enables modeling of cause–effect chains, decision gates, and scheduling dependencies across the coremd system.

---

### 2. 🧠 Core Dimensions

| **Layer** | **Dimension** | **Definition** |
|-----------|---------------|----------------|
| Structural | Cause–Effect Mapping | 1→1, 1→N, N→1, N→N activity chains |
| Logical    | Condition Evaluation | AND, OR, XOR, NAND, NOR, custom logic |
| Temporal   | Dependency Timing    | FS, SS, FF, SF (start/finish constraints) |

---

### 3. 📚 Definitions

- **1→1**: One activity causes one other activity  
- **1→N**: One activity causes multiple activities  
- **N→1**: Multiple activities cause one activity  
- **N→N**: Multiple activities cause multiple activities  
- **AND**: All conditions must be true  
- **OR**: At least one condition must be true  
- **XOR**: Exactly one condition must be true  
- **NAND**: Not all conditions can be true  
- **NOR**: None of the conditions can be true  
- **FS**: Finish-to-Start → A starts after B finishes  
- **SS**: Start-to-Start → A starts after B starts  
- **FF**: Finish-to-Finish → A finishes after B finishes  
- **SF**: Start-to-Finish → A finishes after B starts

---

### 4. 🧪 Examples

| **Scenario** | **Structure** | **Logic** | **Timing** |
|--------------|---------------|-----------|------------|
| Submit form → Receive confirmation | 1→1 | — | FS |
| Policy approved → Notify staff, update system, archive draft | 1→N | AND | FS |
| Complete training, sign contract → Access system | N→1 | AND | SS |
| Submit form, verify ID → Issue card, send email | N→N | OR | FS |

Combined logic example:  
> A AND B → C [FS]  
> “Complete form AND pay fee → Issue license (after both finish)”

---

### 5. 🔗 Integration Points

| **Framework** | **Integration Type** | **Connection** |
|---------------|----------------------|----------------|
| Universal Activity Schema – Directional Logic | Chain Logic | Activities are the units being linked |
| Universal Enforcement Schema – Conditional Outcome Logic | Logic Gate | Enforcement nodes act as conditional triggers |
| Universal Measurement Schema – Quantification Logic | Timing Logic | Length used to model delay, duration, escalation |
| Universal Relationship Schema – Architecture Logic | Flow Logic | ST defines the architecture of conditional chains |
| Universal Relational Geometry – Spatial Logic | Precondition Logic | Spatial relationships act as gating conditions |
| Universal Part Schema – Composition Logic | Scoped Logic | Conditions can apply to specific parts of resources |

---

### 6. 🧭 Visual Schema (Described)

- **Nodes**: Activities (from act01)
- **Arrows**: Conditional links (→)
- **Operators**: Logical gates (AND, OR, etc.)
- **Temporal Tags**: Attached to arrows (e.g. [FS])
- **Enforcement Nodes**: Optional blockers or triggers (from EF)

Example layout:

[A] → [B] ↘ [C] ← [D AND E] [FS] [F]

---

### 7. 🕓 Update History

- Created during ingestion of conditional logic design task
- Populated with structural, logical, and temporal layers
- Expanded with connection tracking logic
- Standardized under coremd-plan format
- Auto-logged in coremd-cl

---

### 8. 🏷️ Tags / Typing

| **Tag** | **Meaning** |
|---------|-------------|
| `AND`   | All conditions must be true |
| `OR`    | At least one condition must be true |
| `XOR`   | Exactly one condition must be true |
| `NAND`  | Not all conditions can be true |
| `NOR`   | None of the conditions can be true |
| `FS`    | Finish-to-Start |
| `SS`    | Start-to-Start |
| `FF`    | Finish-to-Finish |
| `SF`    | Start-to-Finish |
| `1→1`   | One cause → one effect |
| `1→N`   | One cause → multiple effects |
| `N→1`   | Multiple causes → one effect |
| `N→N`   | Multiple causes → multiple effects |

---

© Kelvin Chau, 2025  
This work is part of the [Logic Atlas Framework](https://github.com/kfkchau/logic-atlas/).  
For attribution, citation, or inquiries, please refer to:  
🔗 [https://au.linkedin.com/in/kfkchau](https://au.linkedin.com/in/kfkchau)
