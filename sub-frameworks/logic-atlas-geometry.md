## 🧠 Universal Enforcement Schema – Conditional Outcome Logic

**Alias**: `EF`  
**Formal Name**: Universal Enforcement Schema – Conditional Outcome Logic  

---

### 1. 🧩 Purpose

To model enforcement logic using four dimensions—Scope, Mechanism, Source, and Strength. This schema enables structured modeling of rules, conditions, consequences, and escalation logic across activities, resources, and systems.

---

### 2. 🧠 Core Dimensions

| **Dimension** | **Definition** | **Tag Options** |
|---------------|----------------|-----------------|
| **Scope**     | Who the enforcement applies to | `blanket`, `targeted` |
| **Mechanism** | How enforcement is applied | `incentive`, `deterrent` |
| **Source**    | Where the enforcement originates | `legal`, `policy`, `contract`, `systemic`, `discretion` |
| **Strength**  | How strong the enforcement is | `absolute`, `significant`, `fair`, `minor`, `zero` |

---

### 3. 📚 Definitions

- **Blanket**: Applies to all entities or cases
- **Targeted**: Applies to specific entities or conditions
- **Incentive**: Offers positive outcomes for compliance
- **Deterrent**: Applies negative outcomes for non-compliance
- **Source Types**:
  - `legal`: Statutory or legislative
  - `policy`: Internal or public rules
  - `contract`: Agreement-based
  - `systemic`: Automated or embedded
  - `discretion`: Case-by-case judgment
- **Strength Levels**:
  - `absolute`: E = ∞
  - `significant`: E > C
  - `fair`: E ≈ C
  - `minor`: E < C
  - `zero`: E = 0

---

### 4. 🧪 Examples

| **Scenario** | **Scope** | **Mechanism** | **Source** | **Strength** |
|--------------|-----------|---------------|------------|--------------|
| Tax penalty  | `blanket` | `deterrent`   | `legal`    | `significant` |
| Energy rebate | `targeted` | `incentive` | `policy`   | `fair` |
| Contract breach fine | `targeted` | `deterrent` | `contract` | `absolute` |
| System auto-lock | `blanket` | `deterrent` | `systemic` | `minor` |
| Manager discretion | `targeted` | `incentive` | `discretion` | `variable` |

---

### 5. 🔗 Integration Points

| **Framework** | **Integration Type** | **Connection** |
|---------------|----------------------|----------------|
| Universal Activity Schema – Directional Logic | Trigger/Outcome | Activities are used as conditions and outcomes in enforcement chains |
| Universal Resource Schema – Classification Logic | Enforcement Target | Enforcement applies to specific resource types |
| Universal Relationship Schema – Architecture Logic | Flow Architecture | Enforcement logic follows ST structure |
| Universal Measurement Schema – Quantification Logic | Strength Modeling | Enforcement effort modeled with L/W/H |
| Universal Conditional Logic – Logic Gate | Conditional Node | EF nodes act as gates between activities |
| Universal Part Schema – Composition Logic | Targeted Enforcement | Enforcement can apply to specific parts of a resource |
| Universal Relational Geometry – Spatial Logic | Spatial Targeting | Enforcement can be scoped by spatial relationships (e.g. embedded zones)

Escalation is modeled as a sequence of enforcement nodes, where each outcome becomes a condition for the next enforcement step. This supports progressive enforcement logic (e.g. warning → fine → suspension) without requiring a separate escalation framework.

---

### 6. 🧭 Visual Schema (Described)

- **Enforcement Node**: Box linking condition activity to outcome activity
- **Scope/Mechanism Matrix**: 2×2 grid showing combinations
- **Source Typing**: Color-coded labels (e.g. legal = red, policy = blue)
- **Strength Gradient**: Intensity scale from zero to absolute
- **Flow Arrows**: Show enforcement direction and escalation path
---

### 7. 🕓 Update History

- Created during ingestion of PR-EF.docx, PR-EF 1.docx, PR-EF 2.docx, PR-EF 3.docx
- Refined with strength logic and source typing
- Standardized under coremd-plan format
- Integrated with conditional logic, activity chains, and resource targeting

---

### 8. 🏷️ Tags / Typing

| **Tag**        | **Meaning** |
|----------------|-------------|
| `blanket`      | Applies to all cases |
| `targeted`     | Applies to specific cases |
| `incentive`    | Positive enforcement |
| `deterrent`    | Negative enforcement |
| `legal`        | Statutory source |
| `policy`       | Internal/public rule |
| `contract`     | Agreement-based |
| `systemic`     | Automated enforcement |
| `discretion`   | Case-by-case judgment |
| `absolute`     | E = ∞ |
| `significant`  | E > C |
| `fair`         | E ≈ C |
| `minor`        | E < C |
| `zero`         | E = 0 |

---

© Kelvin Chau, 2025  
This work is part of the [Logic Atlas Framework](https://github.com/kfkchau/logic-atlas/).  
For attribution, citation, or inquiries, please refer to:  
🔗 [https://au.linkedin.com/in/kfkchau](https://au.linkedin.com/in/kfkchau)
