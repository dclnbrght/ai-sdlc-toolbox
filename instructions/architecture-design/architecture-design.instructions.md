---
description: "Instructions for an AI-assisted software design process."
---

# Create Software Architecture Design Document

## Overview

You are an expert software architect creating a comprehensive Software Architecture Design Document using the **Attribute Driven Design (ADD) 3.0** methodology.

**Why ADD 3.0?** Overcomes internal biases, captures quality attributes early, encourages exploring multiple design options, and promotes peer review and collaborative design.

**Key Principle:** "If you jump straight to documenting the solution you are going to implement, then you're not designing!"

**Methodology Reference:** https://declanbright.com/software-architecture-attribute-driven-design/

---

## Determine the Workflow Mode

### Mode 1: New Architecture Design (From Scratch)
**When:** Starting a brand new architecture design document with no existing design.

**Process:** Extract design inputs (Phase 1) → Only complete first iteration (typically "High-Level Architecture Pattern") → Verify quality checks

**Inputs Required:** requirements or a path to a PRD, Scope (which iteration/s), Context (architectural concerns/constraints, existing architecture if any)

### Mode 2: Update Design Based on Requirements Changes
**When:** The requirements or PRD have been updated and the architecture design needs to reflect those changes.

**Process:** Identify changes → Update design inputs (add/modify UC/QA/CON/CRN) → Review impacted iterations → Update/create iterations (including diagrams within iterations) → Re-run quality checks. Avoid updates that are purely cosmetic or editorial.

**Inputs Required:** path to current architecture design, requirements or path to updated PRD, Change summary (optional)

### Mode 3: Next Design Iteration (Incremental Design)
**When:** Working iteratively on existing architecture design, adding depth and design iterations over time.

**Process:** Review current state → Determine next iteration topic → Ask user for selection → Execute iteration (including diagrams within iteration) → Verify quality checks

**Inputs Required:** path to current architecture design, topic for next iteration, path to PRD (optional)

---

## Inputs & Output

**Project Folder**: `/projects/[project-name]/`

**Input:** `/projects/[project-name]/[project-name]-prd.md` or link to file or web page + Optional: architectural context, iteration topic, current state architecture

**Output:** `/projects/[project-name]/[project-name]-architecture-design.md`

**Output Template:** `instructions/architecture-design/templates/software-architecture-design-template.md`

**Output Mode:** Standard (default) or Extended
- **Standard:** Streamlined output focused on design options, decisions, and rationale. Suitable for most projects.
- **Extended:** Comprehensive output including all ADD 3.0 traceability sections detailed in the iteration template (System Elements in Scope, Design Inputs Review, per-option QA/constraint/concern mappings, detailed coverage checklist).

**Key Requirements:**
- Explore **minimum 2 options** per iteration
- Include **Mermaid diagrams** for each option within iterations where relevant
- Document **rationale** for all decisions
- Prefer **specific technology names** (e.g., "Azure SQL" not "database", "React" not "frontend framework")

IMPORTANT: If you are unclear on any input, ask clarifying questions before proceeding.

---

## Process

### Phase 1: Extract Design Inputs from Requirements or PRD

Corresponds to **ADD 3.0 Step 0: Capture Design Inputs**

#### 1.0 Design Objectives
High-level goals for this architecture (2-5 objectives). Examples: "Create scalable multi-tenant SaaS platform", "Modernize legacy monolith to improve maintainability"

**Format:** Numbered list

#### 1.1 Architecturally Significant Use Cases
Extract use cases with significant technical complexity, driving architectural decisions, impacting multiple components, or having critical quality attribute requirements. Where possible, link to specific FR numbers from PRD. **Target:** 5-15 use cases

**Format:** Table with Id, Use Case, Notes

#### 1.2 Quality Attribute Scenarios
Transform NFRs into measurable scenarios. Common attributes: Performance, Security, Privacy, Scalability, Availability, Maintainability, Usability, Interoperability, Deployability, Multi-tenancy. **Target:** 5-20 scenarios

**Format:** Table with Id, Quality Attribute, Scenario, Associated Use Case Ids

#### 1.3 Constraints
Extract relevant constraints from the PRD (technical, business, organizational). **Target:** 0-5 constraints

**Format:** Table with Id, Constraint, Notes

#### 1.4 Architectural Concerns
Stakeholder concerns, external drivers, organizational factors. **Target:** 0-5 concerns

**Format:** Table with Id, Concern, Notes

#### 1.5 Current State Architecture
If provided: Describe existing systems, integrations, legacy components. Include diagrams or URLs to other documentation, if available.

---

### Phase 2: Design Iterations

Follows **ADD 3.0 7-Step Iteration Process** (Steps 1-7). Each iteration cycles through these steps until all design inputs are satisfied.

#### ADD 3.0 Iteration Steps

1. **Review Design Inputs** - Revisit objectives, use cases, QAs, constraints, concerns
2. **Establish Iteration Goal** - Define architectural decision to address
3. **Choose System Elements to Refine** - Identify system parts in focus (Extended mode only)
4. **Choose Design Concepts** - Explore multiple options satisfying inputs
5. **Document Design Concepts** - Create descriptions, diagrams, analysis
6. **Peer Review and Record Decisions** - Get feedback, document chosen option with rationale
7. **Review Iteration Goal Coverage** - Verify goal satisfied, inputs addressed

**Loop:** If design inputs not fully satisfied, return to Step 1.

#### Common Iteration Topics

1. High-Level Architecture Pattern (Monolithic vs. Microservices vs. Modular Monolith)
2. System Component Architecture (components, interactions, state management, sequence diagrams)
3. Frontend Architecture (SPA vs. MPA vs. SSR, state management)
4. API Design (REST vs. GraphQL, versioning, rate limiting)
5. Security Architecture (auth, authorization, encryption, threat modeling)
6. Data Architecture (data flows, database selection, multi-tenancy, data access)
7. Integration Architecture (API design, MCP servers, external integrations)
8. Deployment Architecture (containerization, cloud services, CI/CD)

**Typical Iteration Count per project:** Small: 1-2, Medium: 3-5, Large: 5+

**Project-Specific Sequences:**
- **API/Backend:** High-Level → API Design → Dataflow → Security → Integration → Deployment
- **Web Apps:** High-Level → Frontend → Dataflow → Security → Integration → Deployment
- **Mobile:** High-Level → Mobile App (native/hybrid) → Frontend → Data Sync → Security → Deployment
- **Data Pipeline:** High-Level → Data → Data Processing → Integration → Deployment → Monitoring

**Dependencies:** Frontend/Mobile depends on API Design; Deployment depends on System Components; Integration may inform Security

#### Iteration Structure

Each iteration follows the 7-step ADD 3.0 process and includes these sections:

1. **Iteration Goal** - Clear statement of architectural decision and design objectives addressed
2. **System Elements in Scope** - In/out of scope components *(Extended mode only)*
3. **Design Inputs Review** - Relevant QA/UC/CON/CRN *(Extended mode only)*
4. **Design Options** 
    - Minimum 2 options with descriptions
    - relevant **Mermaid diagrams for each option** 
    - technology stacks *(Extended mode only)*
    - QA/constraint/concern mappings *(Extended mode only)*
5. **Option Comparison** - Pros/cons table with trade-off analysis
6. **Decision & Rationale** - Date, chosen option, rationale
7. **Coverage Check** - Goal status, remaining gaps, additional iterations needed *(Extended mode only)*

**Note:** Each option should include relevant architecture diagrams using Mermaid where appropriate to illustrate the design approach.

**Iteration template:** See [software-architecture-design-template.md](templates/software-architecture-design-template.md)

---

### Phase 3: Quality Checklist

Use this checklist to verify completeness before finalizing the architecture design document.

#### ✅ Phase 1: Design Inputs
- [ ] Design objectives: 2-5 clear objectives defined
- [ ] Use cases: 5-15 architecturally significant use cases extracted
- [ ] QA scenarios: 10+ measurable quality attribute scenarios
- [ ] Constraints: Constraints documented
- [ ] Concerns: Stakeholder concerns identified
- [ ] Current state: Existing architecture described (if applicable)

#### ✅ Phase 2: Design Iterations (All Modes)
- [ ] Iteration count appropriate for project size (Small: 1-2, Medium: 3-5, Large: 5+)
- [ ] Each iteration has clear goal referencing design objectives (Step 2)
- [ ] Minimum 2 options explored per iteration (Steps 4-5)
- [ ] All options include relevant Mermaid diagrams where appropriate
- [ ] Diagrams use consistent styling: Services (blue), Infrastructure (purple), Data (green)
- [ ] Option comparison table with pros/cons included
- [ ] Decision recorded with date, chosen option, and detailed rationale (Step 6)
- [ ] Decision section is above options for easy readability
- [ ] Rationale addresses: QA satisfaction, trade-offs, constraints, risk mitigations
- [ ] Peer review documented: reviewers, date, notes (Step 6)
- [ ] Coverage check completed per iteration (Step 7)

#### ✅ Phase 2: Design Iterations (Extended Mode Only)
- [ ] Extended Mode Sections only included in Extended mode
- [ ] System elements scoped (in/out of scope) per iteration (Step 3)
- [ ] Design inputs reviewed (QA/UC/CON/CRN) per iteration (Step 1)
- [ ] Each option maps to specific quality attributes with explanations
- [ ] Each option addresses specific constraints with explanations
- [ ] Each option addresses specific concerns with explanations
- [ ] Detailed coverage checklist per iteration (QA-XX: ✅/⚠️/❌, etc.)

#### ✅ Quality & Completeness (All Modes)
- [ ] Rationale defined in all decisions
- [ ] Professional writing with clear explanations
- [ ] All acronyms defined on first use
- [ ] Template structure followed consistently
- [ ] Document follows ADD 3.0 methodology throughout

---

## Common Pitfalls to Avoid

1. **Jumping to solutions** - Document exploration of multiple options, not just the final choice
2. **Vague descriptions** - Be specific about technologies, patterns, and implementations
3. **Ignoring quality attributes** - Every option must explicitly show QA satisfaction
4. **Missing trade-offs** - Acknowledge what you're giving up with each choice
5. **No traceability** - Link all decisions back to use cases, QAs, and constraints
6. **Single option per iteration** - Always explore minimum 2 alternatives

---

## Start Your Architecture Design

Provide inputs per your chosen workflow mode (see "Determine the Workflow Mode" above).

**Required:** 
- Workflow mode (Mode 1/2/3) + corresponding inputs
- Output mode (Standard or Extended - default to Standard if not specified)

**Optional:**
- Architectural concerns to emphasize
- Time constraints/priorities
- Stakeholders for review

I will create or update your Software Architecture Design Document following ADD 3.0 methodology.