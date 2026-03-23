## 🧠 Universal Action Schema – Behavioral Tagging Logic

**Alias**: `AT`  
**Formal Name**: Universal Action Schema – Behavioral Tagging Logic  

---

### 1. 🧩 Purpose

To classify and tag actions (verbs) based on their behavioral properties—specifically whether they involve movement and/or transformation. This schema enables consistent tagging of actions across activities, workflows, and enforcement chains.

---

### 2. 🧠 Core Dimensions

| **Dimension**     | **Definition**                          | **Tag Options** |
|-------------------|------------------------------------------|-----------------|
| **Movement**      | Whether the action causes relocation     | `MV`, `NM`, `NA` |
| **Transformation**| Whether the action causes change in form or function | `TF`, `NF`, `NA` |

---

### 3. 📚 Definitions

- **MV** (Move): The action causes relocation (e.g. send, transfer)
- **NM** (No Movement): The action causes stability (e.g. hold, retain)
- **TF** (Transform): The action changes the form or function of the object (e.g. encrypt, convert)
- **NF** (No Transformation): The action prevents change (e.g. lock, preserve)
- **NA** (Not Applicable): The dimension is irrelevant to the action

---

### 4. 🧪 Examples

| **Verb**     | **Movement** | **Transformation** | **Notes** |
|--------------|--------------|--------------------|-----------|
| Send         | `MV`         | `NA`               | Relocates object without changing it |
| Encrypt      | `NM`         | `TF`               | Keeps object in place but transforms it |
| Hold         | `NM`         | `NA`               | No movement or transformation |
| Convert      | `NM`         | `TF`               | Changes form without moving |
| Delete       | `MV`         | `TF`               | Removes and transforms state |
| Approve      | `NA`         | `TF`               | Conceptual transformation only |

---

### 5. 🔗 Integration Points

| **Framework** | **Integration Type** | **Connection** |
|---------------|----------------------|----------------|
| Universal Activity Schema – Directional Logic | Embedded Tagging | Action element is tagged using AT logic |
| Universal Resource Schema – Classification Logic | Action Impact | Actions may consume or transform resources |
| Universal Measurement Schema – Quantification Logic | Action Metrics | Actions can be measured by duration, frequency, intensity |
| Universal Enforcement Schema – Conditional Outcome Logic | Behavior Trigger | Actions may trigger enforcement conditions |
| Universal Conditional Logic – Chain Logic | Trigger Logic | Actions can be used as conditions in logic chains |

---

### 6. 🧭 Visual Schema (Described)

- **Verb Table**: Each verb is tagged with Movement and Transformation dimensions
- **Tag Matrix**: 3×3 grid showing combinations of MV/NM/NA × TF/NF/NA
- **Grey Zone Overlay**: Clarifies ambiguous verbs (e.g. “upload” = `MV`, `NF`)

---

### 7. 🕓 Update History

- Created during initial ingestion phase
- Refined with grey zone logic and tagging examples
- Standardized under coremd-plan format
- Integrated with activity, enforcement, and measurement frameworks

---

### 8. 🏷️ Tags / Typing

| **Tag** | **Meaning** |
|---------|-------------|
| `MV`    | Movement (relocation) |
| `NM`    | No Movement (stability) |
| `TF`    | Transformation (change in form/function) |
| `NF`    | No Transformation (preserve state) |
| `NA`    | Not Applicable |

Every verb or action must be tagged with both dimensions—Movement and Transformation—even if one is [N/A]. This ensures full MECE coverage and avoids ambiguity in compound or partial tagging.

---

© Kelvin Chau, 2025  
This work is part of the [Logic Atlas Framework](https://github.com/kfkchau/logic-atlas/).  
For attribution, citation, or inquiries, please refer to:  
🔗 [https://au.linkedin.com/in/kfkchau](https://au.linkedin.com/in/kfkchau)
