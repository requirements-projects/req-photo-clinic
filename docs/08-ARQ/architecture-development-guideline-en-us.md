# Architecture Development Guideline

This document describes the process for transforming the architectural questionnaire responses into complete and structured architecture documentation. The approach divides the documentation into multiple artifacts to facilitate maintenance, evolution, and understanding of the architecture.

## 0. Directory and File Structure

For better documentation organization and final delivery, we suggest the following directory structure:

```
/04-ARQ/
  ├── 01-introduction/
  │   └── 01-system-overview.md
  │   └── 02-architectural-decisions.md
  │   └── 03-implementation-guidelines.md
  │   └── README.md  # Consolidates all documents in this directory for final delivery.
  │
  ├── 02-application-types/
  │   └── 01-web-architecture.md
  │   └── 02-mobile-architecture.md
  │   └── 03-desktop-architecture.md
  │   └── README.md  # Final delivery document for application types
  │
  ├── 03-infrastructure/
  │   └── 01-cloud-strategy.md
  │   └── 02-provider-specific/
  │       └── aws-architecture.md
  │       └── azure-architecture.md
  │       └── gcp-architecture.md
  │   └── 03-on-premises-architecture.md
  │   └── README.md  # Final delivery document for infrastructure
  │
  ├── 04-deployment/
  │   └── 01-deployment-strategy.md
  │   └── 02-ci-cd-pipeline.md
  │   └── 03-observability-strategy.md
  │   └── README.md  # Final delivery document for deployment
  │
  ├── 05-system-views/
  │   └── 01-system-context.md
  │   └── 02-container-view.md
  │   └── 03-component-view.md
  │   └── 04-code-view.md
  │   └── README.md  # Final delivery document for system views
  │
  ├── 06-architecture-decisions/
  │   └── adrs/  # Directory for Architecture Decision Records
  │   └── 01-architecture-principles.md
  │   └── 02-patterns-antipatterns.md
  │   └── README.md  # Final delivery document for architecture decisions
  │

  ├── architecture-questionnaire-en-us.md  # Internal use only
  ├── questionnaire-responses.md           # Internal use only
  ├── architecture-development-guideline-en-us.md  # This document
  └── arq-analysis-final.md  # Final consolidated architecture document
```

## 1. Process

**Note on README Files:** Each numbered directory in the architecture documentation (e.g., `01-introduction`, `02-application-types`) must contain a `README.md` file. This file is critically important and serves two main purposes:

1.  **Consolidation:** It consolidates the content from all other documents within that directory, providing a complete overview of that specific architectural aspect in a single place.
2.  **Entry Point:** It serves as the primary entry point for any reader. It explains what the section is about and provides a gateway to the more detailed, individual files within the same directory.

Therefore, the `README.md` for each section must be generated as the final step for that section, ensuring the documentation is coherent and easy to navigate.ing Questionnaire Responses

1. Analyze the `questionnaire-responses.md` file containing answers to the architectural questionnaire.
2. Identify target platforms (web/mobile/desktop) from question 8.
3. Identify preferred cloud providers from questions 14 and 22.
4. Extract critical non-functional requirements from questions 6, 19, 42, etc.
5. Identify technical and organizational constraints from questions 7, 50-51, etc.

## 2. Architecture Documentation Development

### 2.1 Introduction Documentation

Create the following documents in the `01-introduction/` folder:

#### overview.md
- Based on answers to questions 1-7
- Include:
  - System objectives
  - Business context
  - Key stakeholders
  - Technical and business challenges to address
  - Project timeline
  - Legacy system integrations
  - Priority quality attributes
  - Known constraints

#### architectural-decisions.md
- List of high-level architectural decisions
- Justifications for each decision
- Considered alternatives
- Accepted trade-offs

#### implementation-guidelines.md
- Architectural principles to follow
- Code and design conventions
- Recommended implementation patterns
- Approved tools and technologies

### 2.2 Application Types Documentation

Based on the answer to question 8, create only the applicable documents:

#### web.md (if applicable)
- Based on answers to question 9
- Include:
  - Type of web application (SPA, MPA, PWA)
  - Browser compatibility requirements
  - Offline functionality strategy (if applicable)
  - SEO and performance requirements
  - Recommended technology stack

#### mobile.md (if applicable)
- Based on answers to question 10
- Include:
  - Supported platforms (iOS/Android)
  - Development approach (native/hybrid/cross-platform)
  - Required device features
  - App store considerations
  - Recommended technology stack

#### desktop.md (if applicable)
- Based on answers to question 11
- Include:
  - Supported operating systems
  - Offline functionality requirements
  - Specific hardware integrations
  - Distribution and update strategy
  - Recommended technology stack

### 2.3 Infrastructure Documentation

#### cloud-agnostic.md
- Based on answers to questions 14-21
- Include:
  - Cloud-agnostic infrastructure architecture
  - Abstracted components (database, storage, etc.)
  - Common interfaces for infrastructure services
  - Cloud portability strategy
  - Compliance and regulatory considerations
  - Backup and disaster recovery strategies

If the client indicated a preference for specific providers in question 22, create additional files for each provider (aws.md, gcp.md, azure.md, etc.), detailing:
- Mapping of abstract components to provider-specific services
- Network and security configurations
- Cost and optimization considerations
- Provider-specific architecture diagrams

### 2.4 Deployment and Continuous Delivery Documentation

#### ci-cd-strategy.md
- Based on answers to questions 23-31
- Include:
  - Release frequency
  - Required environments
  - CI/CD pipeline process
  - Branching strategy
  - QA and approval process
  - Test automation practices

#### observability.md
- Based on question 29
- Include:
  - Logging strategy
  - Metrics to monitor
  - Observability tools
  - Alerts and notifications
  - Recommended dashboards

#### version-management.md
- Based on questions 27, 28, 31
- Include:
  - Semantic versioning policy
  - Rollback strategy
  - Feature flag management
  - Gradual rollout strategy
  - Change communication procedures

### 2.5 System Views

Develop architectural views using the C4 model and 4+1 view model:

#### c4-context.md
- System context diagram
- External actors and systems
- Main communication flows

#### c4-containers.md
- Container diagram
- High-level system components
- Main technologies
- Container responsibilities

#### c4-components.md
- Component diagrams for main containers
- Internal responsibilities
- Interfaces and dependencies
- **Note on Component Naming**:
  - **Initial Diagram**: When first generating this diagram, use generic, domain-agnostic names for the API components (e.g., "Core API Services," "Authentication Service," "Reporting Service"). This helps in focusing on the high-level structure without getting into domain-specific details prematurely.
  - **Final Documentation**: In the final consolidated architecture document, these components must be updated to reflect the fully defined business domains (e.g., "Livestock Management Service," "Financial Control Service").

#### 4plus1-views.md
- Logical view: code structure and organization
- Process view: concurrency and parallelism aspects
- Development view: source code organization
- Physical view: deployment and hardware
- Scenarios: architecturally significant use cases

### 2.6 Architectural Decisions

#### adrs/ (directory)
Create an ADR (Architecture Decision Record) for each significant architectural decision, following the format:
- **Title**: Concise decision name
- **Status**: Proposed, Accepted, Rejected, Deprecated, etc.
- **Context**: What led to this decision
- **Decision**: The decision made
- **Consequences**: Positive and negative impacts
- **Alternatives Considered**: Other options and why they weren't chosen

#### patterns-antipatterns.md
- Catalog of recommended architectural patterns
- List of antipatterns to avoid
- Pattern application examples
- Justifications for selected patterns


## 3. Guidelines for LLM Processing

When processing the questionnaire responses, follow these guidelines:

1. **Complete Analysis**: First read the entire response file to get an overview before starting to produce documents.
2. **Consistency**: Maintain terminology consistency across all generated documents.
3. **Appropriate Abstraction**: Adapt the level of detail according to the documentation stage - more abstract in high-level views, more detailed in domain specifications.
4. **Prioritization**: Reflect clear priorities from the responses in the documentation.
5. **Gap Identification**: Identify and document any missing information that needs clarification.
6. **Diagramming**: Use consistent notation for diagrams (preferably PlantUML or Mermaid for easy Markdown integration).
7. **Traceability**: Maintain references to the questionnaire questions that support specific decisions.
8. **Modularity**: Generate independent but interrelated documents, using cross-references when necessary.
9.  **Contextual Continuity**: Each generated step must be a logical and consistent continuation of the previous one. Before generating a new step, review the output of the preceding step to ensure a coherent and connected narrative throughout the documentation.
10. **Model Completeness**: When generating data models (like entity-relationship diagrams), ensure that the model fully supports all responsibilities and functionalities described for each module in the source artifacts. Every responsibility must be traceable to the entities that implement it.
11. **ERD Simplification**: For clarity, all Entity-Relationship Diagrams (ERDs) must be simplified. They should only display the entity name, its primary key (PK), and any foreign keys (FKs). All other attributes must be detailed in a separate data dictionary, not in the diagram itself.

## 4. Documentation Development Process

1. **Questionnaire Analysis**: Start by completely analyzing the response file.
2. **Directory Structure Creation**: Establish the directories according to the recommended structure.
3. **Progressive Development**:
   1. Start with the introduction documentation
   2. Develop application type documentation as applicable
   3. Document cloud-agnostic infrastructure and specific implementations if needed
   4. Elaborate the deployment strategy
   5. Develop architectural views (C4 and 4+1)
   6. Document architectural decisions (ADRs)


4. **Review and Refinement**: Review all documentation to ensure consistency and completeness.
5. **Index Generation**: Create an index file that links all produced documents.

## 5. Examples and Templates

### Example ADR:

```markdown
# ADR-001: Microservices Architecture Adoption

## Status
Accepted

## Context
The system needs to support high scalability and development by multiple independent teams.

## Decision
We will adopt a microservices-based architecture, with services segregated by business domain.

## Consequences
Positive:
- Independent scalability
- Fault isolation
- Independent development and deployment

Negative:
- Additional operational complexity
- Data consistency challenges
- Additional latency in inter-service communication

## Alternatives Considered
- Modular Monolith: Rejected due to scalability limitations
- Serverless Architecture: Rejected due to migration complexity and state limitations
```

## Conclusion

This guideline provides a complete structure for developing architectural documentation from questionnaire responses. The modular approach keeps documents concise and focused, facilitating maintenance and evolution over time. The resulting documentation should provide a clear view of the system architecture for all stakeholders, from business stakeholders to implementation engineers.
