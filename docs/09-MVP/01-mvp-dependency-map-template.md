# 📑 Module Dependency Map - [Project Name]

**Important:** This is a LLM instruction template. The LLM must generate project-specific content and must NOT copy example text or instructional notes into the final output.

## 1. Overview

**Objective:**  
Summarize the module dependencies for the project. Clearly state which modules depend on others, which can evolve in parallel, and what is the recommended linear build sequence.

---

## 2. Full Module List

List all modules defined in the DQER.

**Example Only – Replace with Project Data:**

| Module ID | Module Name | Description | Priority |
|----|----|----|----|
| MOD-01 | Example Module Name | Short description of the module | Medium |
| MOD-02 | Example Module Name | Short description of the module | Medium |
| ... | ... | ... | Medium |

---

## 3. Dependency Matrix (Module-to-Module)

For each module, list:

- **Depends on:** (List module IDs)
- **Required by:** (List module IDs)
- **Can be developed in parallel:** (Yes / No)

**Example Only – Replace with Project Data:**

### Module: MOD-01 - Example Module Name
- **Depends on:** None
- **Required by:** MOD-03, MOD-04
- **Can be developed in parallel:** Yes

(Repeat this structure for every module.)

---

## 4. Linear Implementation Flow (Recommended Sequence)

List the recommended build sequence based on the dependency analysis.

**LLM Instruction:**  
When suggesting the implementation sequence, the LLM must consider both module dependencies and priority levels (when available). If all priorities are at the default value, sequence should strictly follow dependency order.

**Example Only – Replace with Project Data:**

1. MOD-01 - Example Module Name
2. MOD-02 - Example Module Name
3. MOD-03 - Example Module Name
4. ...

---

## 5. Parallelizable Module Groups

List groups of modules that can evolve in parallel (without dependency conflicts).

**Example Only – Replace with Project Data:**

| Parallel Group | Modules |
|----|----|
| Group A | MOD-01, MOD-02 |
| Group B | MOD-04, MOD-05 |
| ... | ... |

---

## 6. Graphical Flow (Optional)

**If applicable, fill this section with real project data. If not applicable, explicitly write: "This section does not apply to this project due to [reason]".**

**Example Only – Replace with Project Data:**
```
MOD-01 --> MOD-03 --> MOD-04
MOD-02 --> MOD-03
MOD-05 (independent)
```

---

## 7. Observations and Risks Related to Dependencies

**If applicable, fill this section with real project data. If not applicable, explicitly write: "This section does not apply to this project due to [reason]".**

**Example Only – Replace with Project Data:**

- "MOD-03 cannot begin until both MOD-01 and MOD-02 are completed."
- "MOD-05 can proceed at any time and is low risk for integration."

---

## ✅ Final Validation Before Output:

| Validation Check | Required |
|----|----|
| All sections populated with project-specific content | ✅ |
| No example text or instructional notes present in final output | ✅ |
| All module references match real DQER modules | ✅ |
| If a section is optional, decision is explicitly stated (included or justified omission) | ✅ |
| Each module has a priority value (default "Medium" if no project-specific prioritization exists) | ✅ |