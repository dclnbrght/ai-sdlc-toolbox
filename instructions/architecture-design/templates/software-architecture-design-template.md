# {{ Project Name }} - Software Architecture Design

*Based on [ADD 3.0 (Attribute Driven Design)](https://www.sei.cmu.edu/documents/2545/2018_010_001_513930.pdf) software architecture design process from the SEI.*

**Document Version:** {{ 1.0 }}
**Last Updated:** {{ YYYY-MM-DD }}
**Author(s):** {{ Name(s) }}
**Status:** {{ Draft | In Review | Approved }}

---

## Table of Contents

- [Design Objectives](#design-objectives)
- [Definitions & Acronyms](#definitions--acronyms)
- [Design Inputs](#design-inputs)
  - [Architecturally Significant Use Cases](#architecturally-significant-use-cases)
  - [Quality Attribute Scenarios](#quality-attribute-scenarios)
  - [Constraints](#constraints)
  - [Architectural Concerns](#architectural-concerns)
  - [Current State Architecture](#current-state-architecture)
- [Design Iterations](#design-iterations)
  - [{{iteration number and title for each iteration}}]  
    - [{{option number and title for each option}}]
- [Resources](#resources)

---

## Design Objectives

{{ High-level goals for this architecture (2-5 objectives). Examples:
- Create scalable multi-tenant SaaS platform
- Modernize legacy monolith to improve maintainability
- Build secure API-first architecture with extensibility
}}

1. {{ Design objective 1 }}
2. {{ Design objective 2 }}
3. {{ Design objective 3 }}

**Related Documents:**
- Product Requirements Document (PRD): {{ link/path }}
- {{ Other relevant docs }}

---

## Definitions & Acronyms

- **{{ Term }}** - {{ Description }}
- **ADD** - Attribute Driven Design
- **QA** - Quality Attribute
- **UC** - Use Case
- **CON** - Constraint
- **CRN** - Concern

---

## Design Inputs

### Architecturally Significant Use Cases

{{ Extract use cases with significant technical complexity, driving architectural decisions, impacting multiple components, or having critical quality attribute requirements. Target: 5-15 use cases }}

| Id | Use Case | Notes |
|----|----------|-------|
| UC-01 | {{ e.g., User authenticates via OAuth 2.0 }} | {{ Links to PRD FR-XX }} |
| UC-02 | {{ e.g., System processes 1000+ concurrent API requests }} | {{ Links to PRD FR-XX }} |
| UC-03 | {{ Use case description }} | {{ Notes }} |

### Quality Attribute Scenarios

{{ Transform NFRs into measurable scenarios. Common attributes: Performance, Security, Privacy, Scalability, Availability, Maintainability, Usability, Interoperability, Deployability, Multi-tenancy. Target: 5-20 scenarios }}

| Id | Quality Attribute | Scenario | Associated Use Case Ids |
|----|-------------------|----------|-------------------------|
| QA-01 | Performance | {{ e.g., API responds within 200ms for 95% of requests under normal load }} | UC-02 |
| QA-02 | Security | {{ e.g., All API endpoints require authentication and authorization }} | UC-01 |
| QA-03 | Scalability | {{ e.g., System scales horizontally to handle 10x traffic increase }} | UC-02 |
| QA-04 | {{ Quality attribute }} | {{ Measurable scenario }} | {{ UC-XX }} |

### Constraints

{{ Extract related constraints from the PRD (technical, business, organizational). Target: 0-5 constraints }}

| Id | Constraint | Notes |
|----|------------|-------|
| CON-01 | {{ e.g., Must use existing database infrastructure }} | {{ Additional context }} |
| CON-02 | {{ e.g., Development team has X engineers with Y skillset }} | {{ Impact on architecture }} |
| CON-03 | {{ Constraint description }} | {{ Notes }} |

### Architectural Concerns

{{ Stakeholder concerns, external drivers, organizational factors. Target: 0-5 concerns }}

| Id | Concern | Notes |
|----|---------|-------|
| CRN-01 | {{ e.g., Need to support future mobile app integration }} | {{ How this impacts design }} |
| CRN-02 | {{ e.g., Compliance with GDPR data residency requirements }} | {{ Implications }} |
| CRN-03 | {{ Concern description }} | {{ Notes }} |

### Current State Architecture

{{ If applicable: Describe existing systems, integrations, legacy components. Highlight known issues, technical debt or functional limitations. Include diagrams or links to documentation if available. }}

---

## Design Iterations

{{ Each iteration explores architectural decisions following ADD 3.0 methodology. Always include minimum 2 options per iteration. }}

### 1. {{ Iteration Title - e.g., High-Level Architecture Pattern }}

#### Iteration Goal

{{ Clear statement of the architectural decision being made. Example: "Determine the high-level architecture pattern that will best support the system's scalability, maintainability, and team structure requirements." }}

#### Decision & Rationale

{{ IMPORTANT: keep the decision section above the options for easy readability }}

**Date:** {{ YYYY-MM-DD }}

**Chosen Option:** {{ OPTION ID - e.g., OPT-1.1 }} - {{ Option Title }}

**Rationale:**

{{ Succinct explanation including the following where relevant }}

{{ Extended Mode Sections Start }}

{{ 
Addtional Rationale:
- How the chosen option satisfies quality attributes (reference specific QA-XX)
- Key trade-offs and why they are acceptable
- Alignment with design objectives
}}

#### System Elements in Scope

**In Scope:** {{ List components, layers, or subsystems being designed in this iteration }}

**Out of Scope:** {{ List what is explicitly not being addressed in this iteration }}

#### Design Inputs Review

**Quality Attributes:**
- QA-XX: {{ Scenario description }}
- QA-XX: {{ Scenario description }}

**Use Cases:**
- UC-XX: {{ Use case description }}
- UC-XX: {{ Use case description }}

**Constraints:**
- CON-XX: {{ Constraint description }}

**Concerns:**
- CRN-XX: {{ Concern description }}

{{ Extended Mode Sections End }}

#### Option 1.1 - {{ Option Title }}

{{ 
Description including the following where relevant:
- Architecture pattern used (e.g., Microservices, Modular Monolith, Layered)
- Major components and their responsibilities
- Data flows between components
- Communication patterns
- State management approach
Don't include:
- code samples
}}

**Architecture Diagram:**

{{ MERMAID DIAGRAM }}

{{ Extended Mode Sections Start }}

**Satisfies Quality Attributes:**
- **QA-XX:** {{ Specific explanation of how this option satisfies this quality attribute }}

**Addresses Constraints:**
- **CON-XX:** {{ Specific explanation of how this option addresses this constraint }}

**Addresses Concerns:**
- **CRN-XX:** {{ Specific explanation of how this option addresses this concern }}

**Technology Stack:**
- {{ Specific technology 1 - e.g., "MS SQL Server" not "database" }}
- {{ Specific technology 2 - e.g., "React 18 with TypeScript" not "frontend framework" }}
- {{ Additional technologies }}

{{ Extended Mode Sections End }}

#### Option 1.2 - {{ Option Title }}

{{ Same structure as Option 1.1 - detailed description of alternative approach }}

#### Option Comparison

| Option | Pros | Cons | Notes |
|--------|------|------|-------|
| OPT-1.1 | <ul><li>{{ Pro 1 }}</li><li>{{ Pro 2 }}</li></ul> | <ul><li>{{ Con 1 }}</li><li>{{ Con 2 }}</li></ul> | {{ Additional context }} |
| OPT-1.2 | <ul><li>{{ Pro 1 }}</li><li>{{ Pro 2 }}</li></ul> | <ul><li>{{ Con 1 }}</li><li>{{ Con 2 }}</li></ul> | {{ Additional context }} |

{{ Extended Mode Sections Start }}

#### Coverage Check

**Iteration Goal Status:** {{ ✅ Achieved / ⚠️ Partially Achieved / ❌ Not Achieved }}

**Peer Review:**
- **Reviewed By:** {{ Name/Role }}, {{ Name/Role }}
- **Review Date:** {{ YYYY-MM-DD }}
- **Review Notes:** {{ Feedback from peer review, concerns raised, how they were addressed }}

**Design Inputs Addressed:**
- **QA-01:** ✅ Fully addressed - {{ Brief explanation }}
- **QA-02:** ✅ Fully addressed - {{ Brief explanation }}
- **UC-01:** ✅ Fully addressed - {{ Brief explanation }}
- **CON-01:** ✅ Fully addressed - {{ Brief explanation }}
- **CRN-01:** ⚠️ Partially addressed - {{ What remains }}

**Remaining Gaps:** {{ List any quality attributes, use cases, or concerns not yet fully addressed }}

**Additional Iterations Needed:** {{ [ ] Yes - Specify why / [x] No }}

{{ Extended Mode Sections End }}

## Resources

{{ Links to relevant material, external documentation, reference architectures }}

- [ADD 3.0 Methodology](https://www.sei.cmu.edu/documents/2545/2018_010_001_513930.pdf)
- {{ Link to PRD }}
- {{ Link to technical specifications / standards }}
- {{ Link to Threat Model }}
- {{ Reference architecture examples }}
- {{ Team documentation }}