# 🧠 LLM Guideline for MVP Planning (Vertical and Horizontal Approaches)

## Purpose of this Guideline

This guideline provides strict, targeted instructions for LLMs tasked with generating MVP planning documents for a given project. It is designed for internal AI use only and is not intended for human reading or conceptual explanations.

The LLM must analyze previously ingested project documentation (DQER, DUS, dependency matrices, risk lists, business rules, and user journeys) and produce four distinct outputs:

---

## Expected LLM Outputs

| Order | Document | Purpose | Template |
|----|----|----|----|
| 1 | **Module Dependency Map** | Describe the linear and parallel dependency flow between modules, indicating which modules depend on others and which can evolve independently | Use template: `01-mvp-dependency-map-template.md` |
| 2 | **Product Understanding Based on User Stories** | Provide a consolidated narrative and analytical description of the product, focusing on user experience, solved pains, and feature coverage, as derived from user stories | Use template: `02-mvp-project-comprehension-template.md` |
| 3 | **Horizontal MVP Plan** | Propose a delivery strategy based on incremental, end-to-end value releases aligned with user journeys and personas | No fixed template. LLM must generate based on project context and prior documents. |
| 4 | **Vertical MVP Plan** | Propose a module-centric delivery strategy focusing on technical progress and risk reduction, respecting module dependencies | No fixed template. LLM must generate based on project context and prior documents. |

---

## Template Usage Rule for the LLM:

For each document output, the LLM must strictly follow the corresponding template (when available) located under `/docs/MVP/`.

**For MVP Horizontal and Vertical Plans:**  
The LLM is free to structure the document as needed, based on project-specific context, DQER, and DUS. No fixed template exists for these outputs.

### Mandatory LLM Behaviors when Using Templates:

- The LLM must treat each template as a **structural and behavioral execution guide**, not as content.
- **LLMs are strictly forbidden from copying example texts, instructional notes, or placeholder content from the template into the final output.**
- All sections, tables, and snippets in the templates are provided only as structural references. The LLM must replace all example content with project-specific information extracted from the ingested sources.
- For any **optional section**, the LLM must decide, based on the project data, whether to include, fill, or explicitly justify its omission.
- Before finalizing the output, the LLM must conduct an **internal validation**, ensuring:
  - ✅ All sections are populated with project-specific content.
  - ✅ No template instructions or example texts are present in the final output.
  - ✅ All references to modules, user stories, journeys, and personas align with real data from the DQER and DUS.
  - ✅ Optional sections are either properly filled or explicitly marked as not applicable with clear justification.

---

## Input Sources for the LLM

The LLM must fully analyze and consider:

- 📑 DQER (Main and Module-specific documents)
- 📑 DUS (Main and Module-specific documents)
- 📑 Module Dependency Matrix (within the DQER)
- 📑 Business Rules
- 📑 Identified Risks
- 📑 Critical Actions
- 📑 User Journeys and Persona Pains

---

**Important LLM Instruction Regarding Module Files:**

For both the DQER and DUS:

- The main documents act as an index and contain links to individual module files.
- The LLM must **systematically visit, read, and analyze each linked module file individually**, not relying solely on the main document summaries.
- All module-level information (functionalities, user stories, dependencies, actions, etc.) must be extracted directly from the module-specific files.
- Failure to analyze the individual module files will result in incomplete or inaccurate outputs.

---

## Specific Instructions per Output Document

### 1. Module Dependency Map

The LLM must generate:

- A full list of all modules from the DQER
- For each module:
  - Its dependencies (modules it depends on)
  - Its dependents (modules that depend on it)
  - Whether the module can evolve independently (Yes/No)
- A suggested linear implementation flow
- Identification of parallelizable module groups

---

### 2. Product Understanding Based on User Stories

The LLM must:

- Analyze all user stories from the DUS
- Consolidate a narrative that answers:
  - What is the product?
  - What pains does it solve?
  - How will users experience the product?
  - Which personas are impacted?
  - Which user journeys are covered?
- Map user stories to their corresponding journeys and related modules from the DQER

---

### 3. Horizontal MVP Plan

The LLM must:

- Define a sequence of incremental, end-to-end deliveries
- Ensure each step delivers tangible user value
- Link each step to:
  - Personas impacted
  - User Journeys
  - Functionalities from the DQER
  - User Stories from the DUS
- Build the plan incrementally, scaling with each step towards full project scope
- **Output Filename Convention:** The LLM must save this document as `MVP-[ProjectName]-horizontal.md`

---

### 4. Vertical MVP Plan

The LLM must:

- Define a sequence of module or technical-layer-based deliveries
- Respect all documented dependencies
- Clearly list:
  - Modules included per step
  - Functionalities addressed
  - User Stories partially or fully covered
  - Dependencies resolved or pending
- Focus on technical risk reduction and component validation
- Accept that intermediate deliveries may not be fully functional from an end-user perspective
- **Output Filename Convention:** The LLM must save this document as `MVP-[ProjectName]-vertical.md`

---


## MVP Planning Philosophy (Mandatory for Horizontal and Vertical Plans)

When generating both the Horizontal and Vertical MVP plans, the LLM must follow these core philosophical principles:

1. **Prioritize Simplicity and Small Delivery Cycles:**  
   Always prefer smaller, incremental deliveries that reduce complexity, but without breaking critical user journeys.

2. **Accept Incomplete but Functional Journeys:**  
   The LLM must accept that partial module deliveries will leave some user journeys incomplete or partially functional. This is acceptable and expected in early MVP cycles.

3. **Identify Minimal Viable Functional Journeys:**  
   Where possible, prioritize modules and features that allow at least one complete user journey with minimal functionality.

4. **Plan Iterative Value Delivery:**  
   Each iteration should add meaningful value to the user by incrementally expanding functionalities across existing or new journeys.

5. **Evolve Toward Full Coverage:**  
   Continue building upon each iteration until the entire set of modules, functionalities, and user journeys reach 100% completion as defined in the DQER and DUS.

**The LLM must embed this philosophy into every decision when sequencing MVP deliveries.**

## Global LLM Execution Rules

| Rule | Requirement |
|----|----|
| Reference real IDs and names from DQER, DUS, and user journeys | ✅ |
| DO NOT include conceptual explanations about MVP theory | ✅ |
| DO NOT repeat full content from input documents | ✅ |
| YES: Justify step sequencing based on dependencies and user pain coverage | ✅ |
| YES: Ensure contextualized output tied to the real project | ✅ |
| YES: Avoid generic, project-agnostic language | ✅ |
| When defining MVP build sequences, use module priority (from the Module Dependency Map) as a key factor | ✅ |

---

## Execution Note for LLM:

Before generating any document, the LLM must internally process all input sources and validate its understanding of:

- Module dependencies
- User pains and journeys
- Functional and non-functional requirements
- Business rules and critical actions

Final outputs must reflect this understanding and align strictly with the project context.
