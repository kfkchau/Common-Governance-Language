## 🧠 Universal Activity Schema – Directional Logic

**Alias**: `act01`  
**Formal Name**: Universal Activity Schema – Directional Logic  

---

### 1. 🧩 Purpose

To model structured activities using four elemental roles—Actor, Action, Object, Target—and classify each activity by its functional type. This schema enables directional modeling of agency, behavior, and outcome across systems, workflows, and enforcement chains.

---

### 2. 🧠 Core Dimensions

| **Element** | **Definition** | **Notes** |
|-------------|----------------|-----------|
| **Actor**   | The entity initiating the activity | Must have agency (e.g. human, org, system) |
| **Action**  | The verb or behavior performed     | Tagged using AT schema (e.g. MV, TF) |
| **Object**  | The entity affected by the action  | Can be a resource or another activity |
| **Target**  | The destination or recipient       | Can be a resource, actor, or system |

Each activity includes temporal metadata: start time, end time, and recurrence. Recurrence is modeled via loop-back connectors with a measurement count tag (e.g. “repeat = 3”), enabling tracking of repeated or cyclical behavior.

---

### 3. 📚 Definitions

- **Activity**: A structured event composed of Actor, Action, Object, and Target.
- **Activity Types**:
  - `REQ` (Requirement): Expected or mandated activity
  - `EVT` (Event Record): Logged or completed activity
  - `CAP` (Capability): Potential or available activity

---

### 4. 🧪 Examples

| **Scenario** | **Actor** | **Action** | **Object** | **Target** | **Type** |
|--------------|-----------|------------|------------|------------|----------|
| Staff sends report to manager | Staff | Send | Report | Manager | REQ |
| System encrypts file | System | Encrypt | File | Storage | EVT |
| Team prepares draft | Team | Prepare | Draft | Review queue | CAP |

Nested example:  
> CIO approves new patching requirement → contains:  
> `REQ`: System owners send patching records to business owners.

---

### 5. 🔗 Integration Points

| **Framework** | **Integration Type** | **Connection** |
|---------------|----------------------|----------------|
| Universal Action Schema – Behavioral Tagging Logic | Tagging | Action element is tagged using AT logic (MV, TF, etc.) |
| Universal Resource Schema – Classification Logic | Object/Target Typing | Object and Target are typed using RS categories |
| Universal Enforcement Schema – Conditional Outcome Logic | Trigger/Condition | Activities are used in enforcement chains |
| Universal Measurement Schema – Quantification Logic | Attribute Tagging | Activities tagged with Length, Width, Height |
| Universal Relationship Schema – Architecture Logic | Flow Mapping | Activities linked via directional flows |
| Universal Relational Geometry – Spatial Logic | Spatial Context | Activities scoped spatially |
| Universal Part Schema – Composition Logic | Target/Object Scoping | Activities target specific parts of a resource |
| Universal Conditional Logic – Activity Linkage | Chain Logic | Activities linked via conditional operators and temporal dependencies |

---

### 6. 🧭 Visual Schema (Described)

- **Activity Node**: Box with four compartments (Actor, Action, Object, Target)
- **Type Tag**: Label (REQ, EVT, CAP)
- **Flow Arrows**: Connect activities in sequence or conditional chains
- **Spatial Overlay**: Optional Venn2 tags for location/context
- **Measurement Tags**: Optional L/W/H vectors

---

### 7. 🕓 Update History

- Created during initial ingestion phase
- Expanded with nested activity logic and multi-agent chains
- Standardized under coremd-plan format
- Integrated with conditional logic, measurement, and spatial overlays

---

### 8. 🏷️ Tags / Typing

| **Tag** | **Meaning** |
|---------|-------------|
| `REQ`   | Required activity |
| `EVT`   | Logged or completed activity |
| `CAP`   | Capability or potential activity |
| `ACTOR_TYPE` | Human, Org, System, Agent |
| `ACTION_TAG` | MV, TF, etc. from AT schema |
| `RESOURCE_TYPE` | PH, VI, CO, NC from RS schema |

---

© Kelvin Chau, 2025  
This work is part of the [Logic Atlas Framework](https://github.com/kfkchau/logic-atlas/).  
For attribution, citation, or inquiries, please refer to:  
🔗 [https://au.linkedin.com/in/kfkchau](https://au.linkedin.com/in/kfkchau)
