# Artifact Analysis Guideline for Architectural Requirements

## 1. Purpose
This document provides a structured approach to analyze existing project artifacts (Project Charter, DQER modules, DUS modules) to extract architectural requirements and answer the architecture questionnaire.

## 2. Artifact Analysis Framework

### 2.1 Project Charter (TAP) Analysis
**Objective:** Understand the project scope, objectives, and high-level requirements.

**Key Information to Extract:**
- Project goals and success criteria
- Stakeholder identification and roles
- Project scope boundaries
- High-level assumptions and constraints
- Initial technical vision and approach
- Key business drivers and justification
- Project risks and dependencies

### 2.2 Document of Scope Qualification and Requirements (DQER) Analysis
**Objective:** Extract detailed functional and non-functional requirements from both the main document and module-specific files.

#### 2.2.1 Main DQER Document Analysis
**Key Information to Extract:**
- System purpose and target audience
- Overall system objectives
- High-level system architecture
- Cross-cutting requirements
- System-wide constraints
- Integration points and external systems

#### 2.2.2 DQER Module Documents Analysis
**Key Information to Extract:**
- Module abbreviation and identifier
- Module implementation status
- Module description and purpose
- Initial scope definition
- Detailed functionalities and features
- Module-specific constraints
- Data structure and field requirements
- Module interactions and dependencies
- Business rules specific to the module

### 2.3 Definition of User Stories (DUS) Analysis
**Objective:** Understand functional requirements from a user perspective across all modules.

#### 2.3.1 Main DUS Document Analysis
**Key Information to Extract:**
- Overall user story structure and organization
- System domains and module categorization
- Key personas and user roles
- Cross-cutting user needs

#### 2.3.2 DUS Module Documents Analysis
**Key Information to Extract:**
- User stories for each module (including IDs like US-MBF-001)
- User roles and personas per functionality
- Detailed acceptance criteria
- Technical implementation notes
- DQER references and traceability
- Problems addressed by each story
- Offline operation requirements
- Reporting and visualization needs

### 2.4 Existing Modules Analysis
**Objective:** Understand existing modules and organize them into domains.

**Key Information to Extract:**
- Module specifications and boundaries
- Fields and data structures
- Business rules implemented per module
- Relationships between modules
- Data flows and dependencies
- Technical constraints of each module
- Existing architecture patterns

## 3. Analysis Process

### 3.1 Initial Artifact Review
1. **Inventory all available artifacts**
   - List all TAP, TQ, ER, and DUS documents
   - Note versions and last update dates
   - Identify any gaps in documentation

2. **Extract architectural characteristics**
   - Create a matrix mapping requirements to architectural qualities
   - Identify conflicting requirements
   - Note any implicit requirements

### 3.2 Domain Analysis
1. **Identify bounded contexts**
   - Group related user stories and entities
   - Define context boundaries
   - Document context maps

2. **Extract business rules**
   - List all explicit business rules
   - Document rule priorities and variability points
   - Identify business events and commands

### 3.3 Entity and Relationship Analysis

1.  **Ensure Complete Coverage of Responsibilities**
    -   **CRITICAL**: When defining entities and their relationships, you must ensure that the resulting data model fully supports all responsibilities and functionalities described in the DQER and DUS module documents. Each responsibility must be traceable to the entities that implement it.
    -   Create a mapping table or checklist to verify that no functional requirement has been overlooked in the data model.

2.  **Simplify Entity-Relationship Diagrams (ERDs)**
    -   To maintain clarity and focus on high-level structure, ERDs included in the documentation must be simplified.
    -   **Guideline**: Diagrams should only display the entity name, its primary key (PK), and any foreign keys (FKs) that establish relationships. All other descriptive attributes (e.g., name, description, timestamps) should be omitted from the diagram and detailed in the accompanying data dictionary table.

### 3.4 Technical Requirements Analysis
1. **Identify architectural drivers**
   - List quality attribute scenarios
   - Document technical constraints
   - Identify cross-cutting concerns

2. **Map to architectural views**
   - Create logical view of the system
   - Document deployment scenarios
   - Identify component interactions

### 3.4 Module Domain Grouping
1. **Analyze existing module structure from DQER and DUS**
   - Identify all modules based on the DQER module files (like `04-Membros-fazenda.md`)
   - Extract module identifiers and abbreviations (e.g., MBF for Membros da Fazenda)
   - Correlate modules with their corresponding DUS documents
   - Document the implementation status (backend, frontend, mobile, backoffice)

2. **Group modules by domain based on business functionality**
   - Use the domain categorization from the main DUS document (section 4 - Domains and System Modules)
   - Group related modules into coherent domains (e.g., Security, Farm Management, Livestock)
   - Document cross-domain dependencies and interactions
   - Map modules to domain-driven design concepts (entities, aggregates, services)

3. **Extract module business rules and specifications**
   - From DQER: Extract module descriptions, scope, and functionalities
   - From DUS: Extract user stories, acceptance criteria, and technical notes
   - Identify module-specific constraints and requirements
   - Document interfaces between modules and their contracts

4. **Create module relationship diagrams**
   - Map data flows between modules
   - Identify synchronization requirements (especially for offline operation)
   - Document dependencies and integration points
   - Highlight critical path modules essential for system functioning

## 4. Questionnaire Response Generation

### 4.1 Directory Structure and Output Files
1. **Create analysis directory structure:**
   ```
   /04-ARQ/
     └── arq-artifact-analysis/
         ├── project-charter-analysis.md
         ├── dqer-main-analysis.md
         ├── dqer-modules/
         │   ├── module1-analysis.md
         │   ├── module2-analysis.md
         │   └── ...
         ├── dus-main-analysis.md
         ├── dus-modules/
         │   ├── module1-analysis.md
         │   ├── module2-analysis.md
         │   └── ...
         ├── artifact-questionnaire-answers.md
         └── remaining-unanswered-questions.md
   ```

2. **Document Structure for Analysis Files:**
   - Each artifact analysis document should include:
     - Source artifact information (filename, version, date)
     - Extracted requirements and architectural implications
     - Questionnaire items addressed by the artifact
     - Key findings and insights

### 4.2 Filling Questionnaire Responses
1. **For each question in the architecture questionnaire:**
   - Reference the source artifact (TAP/TQ/ER/DUS)
   - Quote relevant sections
   - Note any assumptions made
   - Flag any missing information

2. **Prioritize responses**
   - Mark high-impact architectural decisions
   - Identify areas needing further clarification
   - Document any trade-offs considered

### 4.3 Consolidating Questionnaire Answers
1. **Generate artifact-questionnaire-answers.md**
   - Compile all answers extracted from artifacts
   - Organize by questionnaire section and question number
   - Include source references (exact artifact and section)
   - Add confidence level for each answer (high/medium/low)
   - Document any assumptions or interpretations made

2. **Generate remaining-unanswered-questions.md**
   - List all questions that could not be answered through artifact analysis
   - Include partial information found, if any
   - Note why existing artifacts don't provide sufficient information
   - Categorize unanswered questions (technical, business, organizational)
   - Prioritize questions based on architectural impact

3. **Direct question answering process**
   - Schedule sessions with stakeholders for addressing unanswered questions
   - Document responses directly in remaining-unanswered-questions.md
   - Record the source of each answer (stakeholder name, role, date)
   - Flag answers that may need further validation

## 5. Output Artifacts

### 5.1 Primary Output Files
- **artifact-questionnaire-answers.md**: Consolidated answers to all questionnaire items
- **remaining-unanswered-questions.md**: Questions that couldn't be answered through artifact analysis

### 5.2 Supporting Analysis Files
- **project-charter-analysis.md**: Analysis of the Project Charter (TAP)
- **dqer-main-analysis.md**: Analysis of the main DQER document
- **dqer-modules/**: Directory containing analyses of individual DQER modules
- **dus-main-analysis.md**: Analysis of the main DUS document
- **dus-modules/**: Directory containing analyses of individual DUS modules

### 5.3 Domain Analysis Document
- Module grouping by domains
- Module relationship diagrams
- Cross-domain dependencies
- Key business rules by domain

### 5.4 Architecture Decision Records (ADRs)
- Key decisions made during analysis
- Rationale and alternatives considered
- Impact assessment on modules and domains
- References to specific modules or user stories affected

## 6. Validation Process

### 6.1 Review Sessions
- Conduct walkthroughs with stakeholders
- Validate assumptions
- Resolve conflicts

### 6.2 Documentation Review
- Verify traceability to source artifacts
- Ensure consistency across documents
- Validate technical feasibility

## 7. Tools and Templates

### 7.1 Analysis Templates
- Module extraction template (for listing and categorizing all DQER/DUS modules)
- Domain grouping matrix (for organizing modules into domains)
- Architectural questionnaire mapping template (for tracing questions to artifact sources)
- Traceability matrix (linking requirements to architectural decisions)
- Decision log template (for documenting architectural choices)
- Direct question answering template (for unanswered questionnaire items)

### 7.2 Recommended Tools
- Diagramming tools (e.g., draw.io, Lucidchart)
- Documentation tools (e.g., Confluence, Notion)
- Version control for documentation

## 8. Next Steps

1. **Set up artifact analysis directory structure**
   - Create `/04-ARQ/arq-artifact-analysis/` directory
   - Set up subdirectories for module analyses

2. **Inventory all Project Charter, DQER and DUS artifacts**
   - Create a complete list of all module files and their locations
   - Verify document versions and status

3. **Perform systematic artifact analysis**
   - Analyze Project Charter document
   - Analyze main DQER document and all module files
   - Analyze main DUS document and all module files
   - Document findings in respective analysis files

4. **Extract architecture questionnaire answers**
   - Map artifact content to questionnaire items
   - Document sources and references
   - Generate `artifact-questionnaire-answers.md`

5. **Identify unanswered questions**
   - Create `remaining-unanswered-questions.md` for gaps
   - Prioritize questions needing direct stakeholder input

6. **Address remaining questions**
   - Schedule sessions with stakeholders
   - Document direct answers in `remaining-unanswered-questions.md`

7. **Group existing modules by domains**
   - Use domain categories from the main DUS document
   - Document cross-domain dependencies
   - Create domain boundary diagrams

8. **Review and validate with architecture team**
   - Conduct architecture review sessions
   - Validate domain boundaries and relationships
   - Confirm architectural decisions

9. **Finalize architectural documentation**
   - Generate final architecture documents based on questionnaire answers
   - Ensure traceability to source artifacts
   - Create complete architecture document structure
