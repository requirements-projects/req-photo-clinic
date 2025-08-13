# 📑 Product Understanding Based on User Stories - [Project Name]

**Important:** This is a LLM instruction template. The LLM must generate project-specific content and must NOT copy example text or instructional notes into the final output.

## 1. Product Overview (Narrative Summary)

**Objective:**  
Provide a high-level narrative that explains what the product is, what problem it solves, and how it delivers value to the end user.

**LLM Instruction:**  
Write in a clear and objective tone. Focus on the user-facing perspective (not technical architecture). Use real personas and real pains extracted from the DQER and DUS.

**Example Only – Replace with Project Data:**
```
The [Project Name] platform is designed to enable [Persona Names] to [solve specific pains], by providing features such as [Feature Summaries]. Through its core modules, the product facilitates [key user activities], delivering measurable benefits like [expected outcomes].
```

---

## 2. Personas and User Pains Addressed

**Objective:**  
List all personas covered in the DUS and link them to the primary pains the product addresses.

**Example Only – Replace with Project Data:**

| Persona | Pain Points Addressed |
|----|----|
| Persona 1 | Pain A, Pain B |
| Persona 2 | Pain C, Pain D |
| ... | ... |

---

## 3. User Journeys and Functional Coverage

**Objective:**  
Show how the user journeys (from DUS) are covered by the user stories and modules.

**LLM Instruction:**  
For each journey:

- Describe the sequence of user interactions.
- Map which user stories cover each step.
- Map which modules implement each part.

**Example Only – Replace with Project Data:**

### Journey: [Journey Name]
- **User Goal:** [Summary of the goal]
- **Flow:**
  1. Step 1 - [Brief Description]  
     - User Story: [Story ID]  
     - Module: [Module ID]
  2. Step 2 - [Brief Description]  
     - User Story: [Story ID]  
     - Module: [Module ID]
  3. ...
- **Personas Involved:** [Persona Names]

(Repeat for each journey)

---

## 4. Functional Areas (By User Story Grouping)

**Objective:**  
Organize the product into functional areas, each representing a logical grouping of user stories that together build a specific part of the system.

**LLM Instruction:**  
Propose logical areas based on DUS story groupings and DQER modules.

**Example Only – Replace with Project Data:**

### Functional Area: [Area Name]
- **Purpose:** [Short summary]
- **User Stories:**
  - [Story ID] - [Story Title]
  - [Story ID] - [Story Title]
  - ...

**Related User Journeys:**  
For each functional area, list all user journeys impacted by its user stories. Use real journey names and IDs from the DUS.

- [Journey ID] - [Journey Name]
- [Journey ID] - [Journey Name]
- ...

(Repeat for each functional area)

---

## 5. End-to-End Experience Map (Optional)

**If applicable, fill this section with real project data. If not applicable, explicitly write: "This section does not apply to this project due to [reason]".**

**Example Only – Replace with Project Data:**
```
A [Persona Name] starts by accessing the [Module/Screen], proceeds to [Next Interaction], then completes [Final Goal]. Throughout this experience, the system manages [state transitions], handles [business rules], and ensures [non-functional requirements like performance/security].
```

---

## ✅ Final Validation Before Output:

| Validation Check                                                                                    | Required   |
|-----------------------------------------------------------------------------------------------------|------------|
| All sections populated with project-specific content                                                | ✅          |
| No example text or instructional notes present in final output                                      | ✅          |
| All user story and module references match real project data                                        | ✅          |
| Optional sections explicitly included or omitted with justification                                 | ✅          |
| Each functional area includes a "**Related User Journeys**" subsection listing all related journeys | ✅          |
