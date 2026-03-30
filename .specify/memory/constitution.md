# IF Hub Constitution

## Core Principles

### I. Compliance-First Managed Services
Managed services are allowed only when they can be documented as compatible with GDPR, EU data residency expectations, and Swedish legal obligations. Every production dependency that processes personal data MUST have a documented owner, DPA/sub-processor review, retention decision, and fallback/exit strategy before launch.

### II. Extensible Identity and Payment Providers
BankID and Freja+ are mandatory identity providers for the MVP, and the platform MUST stay ready for future providers such as MitID through explicit provider interfaces and adapter boundaries. Swish and card payments are mandatory payment rails for the MVP, and payment workflows MUST use internal contracts, idempotent event handling, and provider-agnostic status models.

### III. Attendance-First Club Operations
The primary club workflow is attendance registration, and the product MUST hide downstream administrative complexity from coaches and volunteers. LOK qualification, export preparation, submission attempts, and audit logging MUST run in the background with clear recovery paths for failed or disputed submissions.

### IV. Bilingual by Default
All member-facing and staff-facing flows shipped to production MUST be complete in Swedish and English at the same release quality bar. Localized product copy MUST be versioned in the repository, no production flow may depend on untranslated hardcoded text, and any managed translation service MUST synchronize back to repository-owned source files.

### V. Spec-Driven, Testable Boundaries
Requirements, plans, and tasks MUST be captured in spec-kit artifacts before implementation begins for a deliverable. Every epic MUST map to independently testable user stories, explicit acceptance criteria, and the appropriate validation layer (unit, integration, end-to-end, compliance, or operational checks).

## Delivery Constraints

- Default architecture direction for the current product vision is Flutter clients, Supabase/Postgres backend capabilities, and dedicated adapter layers for identity, payments, LOK automation, and localization workflows.
- Sensitive domains such as identity verification, payments, attendance, and LOK reporting MUST expose audit-friendly events and explicit error handling.
- Release readiness for MVP features requires documented data ownership, role-based access expectations, and rollback procedures for managed integrations.

## Workflow and Review Gates

- Follow the spec-kit sequence: constitution -> specify -> plan -> tasks -> implementation.
- New epics require a linked spec folder under `/specs/` before milestone commitment.
- Work that changes identity, payment, or LOK behavior requires an explicit compliance and operational review in the plan artifact.
- Pull requests must stay scoped to one spec concern and update related roadmap artifacts when priorities change.

## Governance

This constitution overrides ad hoc delivery preferences when they conflict with compliance, testability, or maintainability. Amendments require a pull request that updates this file, explains the reason for change, and identifies any backlog or roadmap artifacts that must be realigned.

**Version**: 1.0.0 | **Ratified**: 2026-03-30 | **Last Amended**: 2026-03-30
