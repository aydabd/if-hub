# Feature Specification: Platform Foundation and Club Operations MVP

**Feature Branch**: `[001-platform-foundation]`  
**Created**: 2026-03-30  
**Status**: Draft  
**Input**: User description: "Initiera spec-kit i första PR. And then start create wpic stories and milestones"

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Establish a compliant product baseline (Priority: P1)

As a product owner, I want the platform scope, compliance assumptions, and delivery boundaries documented in spec-kit so the team can start implementation from a governed baseline instead of ad hoc decisions.

**Why this priority**: Without a shared baseline, identity, payments, and LOK automation risk drifting into incompatible or non-compliant solutions.

**Independent Test**: Reviewers can verify this story by checking that the constitution, spec, roadmap, and issue templates describe the same MVP scope and decision rules.

**Acceptance Scenarios**:

1. **Given** the repository is opened by a contributor, **When** they inspect the spec-kit artifacts, **Then** they can find the core product principles, MVP scope, and delivery workflow without relying on tribal knowledge.
2. **Given** a new epic is proposed, **When** the contributor uses the repository backlog assets, **Then** the epic can be mapped to a milestone, user stories, and acceptance criteria.

---

### User Story 2 - Let coaches focus on attendance while LOK runs in the background (Priority: P1)

As a coach or club volunteer, I want attendance registration to be the primary operational workflow so the system can handle LOK qualification, export, and submission preparation with minimal extra administration.

**Why this priority**: Attendance and LOK automation are central value drivers for clubs and differentiate the platform from generic membership systems.

**Independent Test**: The story is covered if the spec defines the attendance-to-LOK flow, required auditability, and fallback handling for failed automated submissions.

**Acceptance Scenarios**:

1. **Given** an activity with registered attendance, **When** the workflow qualifies for LOK support, **Then** the system prepares export and submission artifacts without requiring duplicate data entry.
2. **Given** a submission fails or is disputed, **When** an administrator inspects the record, **Then** the system exposes enough audit history to retry or correct the submission.

---

### User Story 3 - Support Swedish eID from day one with room to extend (Priority: P1)

As a member or guardian, I want to sign in and verify my identity with trusted local providers such as BankID and Freja+ so the club can use secure flows that are familiar in Sweden.

**Why this priority**: Trusted identity is required for secure onboarding, payments, and sensitive member workflows.

**Independent Test**: The story is independently testable when the specification defines mandatory providers, provider-agnostic extension points, and failure handling expectations.

**Acceptance Scenarios**:

1. **Given** a supported identity provider is available, **When** a member starts verification, **Then** the platform can map the verified identity to an internal user and person record.
2. **Given** a future provider such as MitID is approved, **When** the platform extends identity support, **Then** the new provider can be added through the same adapter contract without redesigning the core domain.

---

### User Story 4 - Accept payments through Swedish-first rails (Priority: P2)

As a guardian or member, I want to pay club fees with Swish or card so I can use common payment methods without manual reconciliation by the club.

**Why this priority**: Payments are required for a viable club operations platform, but they can follow once the compliance and attendance foundations are clear.

**Independent Test**: The story is independently testable when the specification defines supported payment rails, reconciliation expectations, webhook/idempotency rules, and audit requirements.

**Acceptance Scenarios**:

1. **Given** a payable fee exists, **When** the payer selects Swish or card, **Then** the platform creates a payment attempt and updates the internal status model consistently.
2. **Given** a provider sends duplicate callbacks or delayed status updates, **When** the platform reconciles the event, **Then** the internal payment state remains correct and auditable.

---

### User Story 5 - Ship a fully bilingual MVP (Priority: P2)

As a user of the app, I want the interface to be complete in Swedish and English so the product works for both local and international stakeholders from launch.

**Why this priority**: Language completeness affects trust, adoption, and supportability, but it depends on the base product flows being defined first.

**Independent Test**: This story is independently testable when the specification defines the supported languages, completeness bar, repository source of truth, and managed translation workflow expectations.

**Acceptance Scenarios**:

1. **Given** a supported production flow, **When** the user switches between Swedish and English, **Then** the same workflow remains complete and understandable in both languages.
2. **Given** a new release candidate, **When** localization review runs, **Then** missing or inconsistent translations block release readiness for affected flows.

---

### Edge Cases

- What happens when a managed service satisfies EU hosting requirements but its sub-processor chain changes after go-live?
- How does the system handle an identity provider outage during sign-in or identity linking?
- How does the system recover when a LOK submission is prepared from incomplete attendance data?
- What happens when a payment provider sends duplicate, out-of-order, or failed status callbacks?
- How does the release process detect missing Swedish or English translations before production?

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: The repository MUST include spec-kit scaffolding and a project constitution that defines compliance, workflow, and quality rules.
- **FR-002**: The product specification MUST document GDPR-aware managed service usage expectations, including EU/Sweden compliance checkpoints.
- **FR-003**: The MVP MUST support BankID as a mandatory identity provider.
- **FR-004**: The MVP MUST support Freja+ as a mandatory identity provider.
- **FR-005**: The identity domain MUST support adding future providers through a provider-agnostic integration contract.
- **FR-006**: The MVP MUST treat attendance registration as the primary club workflow for LOK-related operations.
- **FR-007**: The platform MUST automate LOK qualification, export preparation, and submission tracking from attendance data.
- **FR-008**: The platform MUST retain an audit trail for LOK evaluations and submission attempts.
- **FR-009**: The MVP MUST support Swish payments.
- **FR-010**: The MVP MUST support card payments.
- **FR-011**: Payment processing MUST use an internal status model that is resilient to duplicate or delayed provider events.
- **FR-012**: The MVP MUST ship with Swedish and English as fully supported product languages.
- **FR-013**: Localization source files MUST be owned in the repository even if a managed translation platform is used.
- **FR-014**: Backlog planning MUST define epics, user stories, and milestone groupings for the MVP.
- **FR-015**: New backlog items MUST be representable through repository issue templates for epics and user stories.

### Key Entities *(include if feature involves data)*

- **Club**: A tenant-level organization that owns teams, members, fees, and compliance decisions.
- **Person**: A real-world individual such as a member, guardian, coach, or administrator.
- **User Account**: A product login identity mapped to one or more verified identities and roles.
- **Identity Provider**: A supported verification source such as BankID, Freja+, or a future national eID.
- **Verification Session**: A trackable attempt to verify or sign in through an external identity provider.
- **Activity**: A club event where attendance is registered and evaluated for downstream reporting.
- **Attendance Record**: Participation data recorded for an activity by coaches or administrators.
- **LOK Submission Batch**: A generated reporting artifact and status record built from eligible attendance data.
- **Payment Attempt**: An internal record that tracks a Swish or card payment through provider callbacks and reconciliation.
- **Localization Resource**: Repository-owned translation content for Swedish, English, and future languages.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A new contributor can identify the platform principles, MVP scope, and workflow from repository artifacts in under 15 minutes.
- **SC-002**: Every MVP backlog item can be mapped to one epic, at least one user story, and one milestone without ambiguity.
- **SC-003**: The initial roadmap covers identity, attendance/LOK, payments, localization, and compliance as explicit milestone outcomes.
- **SC-004**: Reviewers can trace each mandatory user requirement in this document to at least one planned implementation task.

## Assumptions

- The team will use GitHub issues and milestones for operational tracking after the repository-level templates and roadmap are agreed.
- Flutter, Supabase/Postgres, and managed translation tooling remain the current working architecture assumptions until replaced by a future plan artifact.
- MVP scope focuses on Sweden first, with future Nordic identity expansion treated as an extension of the same provider model.
- Automated LOK submission may require staged rollout with manual approval or retry steps even when the long-term goal is end-to-end automation.
