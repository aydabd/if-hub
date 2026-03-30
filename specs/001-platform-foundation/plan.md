# Implementation Plan: Platform Foundation and Club Operations MVP

**Branch**: `[001-platform-foundation]` | **Date**: 2026-03-30 | **Spec**: `/home/runner/work/if-hub/if-hub/specs/001-platform-foundation/spec.md`

## Summary

Bootstrap the repository for spec-driven delivery, establish the governing constitution, and define the initial product backlog around the MVP outcomes: compliant managed services, extensible Swedish-first identity, attendance-first LOK automation, integrated payments, and bilingual delivery.

## Technical Context

### Proposed Direction

- **Client applications**: Flutter for mobile-first attendance workflows and shared UI foundations
- **Backend platform**: Supabase/Postgres for core data, auth session support, storage, and row-level security foundations
- **Domain boundaries**: Dedicated adapters for identity providers, payment providers, LOK automation, and localization workflow integration
- **Localization workflow**: Repository-owned source strings synchronized with a managed translation platform

### Architecture Decisions to Preserve

1. **Compliance-first managed services**: Each managed dependency must be approved against GDPR/EU/Sverige expectations before production rollout.
2. **Provider-agnostic identity**: BankID and Freja+ are mandatory, but the domain model must support future providers such as MitID through adapters.
3. **Attendance-first operations**: Coaches should only need to work with attendance; LOK reporting concerns stay behind the scenes.
4. **Payment abstraction**: Swish and card use separate provider adapters behind an internal payment state model.
5. **Bilingual release bar**: Swedish and English remain complete and repository-traceable in every production release.

## Epic Backlog

### Epic 1 - Spec and Governance Foundation
- Establish constitution, spec artifacts, and issue templates.
- Align roadmap and milestone planning with spec-kit workflow.
- Outcome: the team has a governed way to define future work.

### Epic 2 - Identity and Access Foundation
- Define user, person, identity-provider, and verification-session models.
- Prepare BankID and Freja+ adapter contracts with a future-provider extension path.
- Outcome: trusted sign-in and verification can be implemented without redesigning the domain.

### Epic 3 - Attendance and LOK Automation
- Define activity, attendance, LOK evaluation, export, and submission workflows.
- Capture audit and fallback expectations for failed automation.
- Outcome: clubs can treat attendance as the only required frontline action.

### Epic 4 - Payments and Reconciliation
- Define fee, payment-attempt, event, and reconciliation models.
- Cover Swish and card flows behind one internal status lifecycle.
- Outcome: clubs can collect fees with minimal manual bookkeeping.

### Epic 5 - Localization and Content Operations
- Define repository-owned localization sources and managed translation workflow.
- Set release gates for Swedish and English completeness.
- Outcome: bilingual quality is enforced from the start.

## Milestone Outline

### Milestone 1 - Governance and Product Baseline
**Goal**: Finish the initial spec-kit setup and agree on constitution, MVP scope, and roadmap.

**Exit criteria**:
- Constitution approved
- Initial MVP spec approved
- Epic and milestone roadmap approved
- Epic and story issue templates available

### Milestone 2 - Identity and Tenant Foundation
**Goal**: Lock the data and workflow design for tenants, people, roles, and eID adapters.

**Exit criteria**:
- Identity contracts documented
- Core entities and access model agreed
- Compliance review started for managed identity dependencies

### Milestone 3 - Attendance and LOK Operations
**Goal**: Define the operational flow that turns attendance into automatable LOK reporting.

**Exit criteria**:
- Attendance workflow approved
- LOK evaluation and audit model approved
- Retry/manual fallback path documented

### Milestone 4 - Payments and Localization
**Goal**: Finalize payment and language requirements for MVP delivery.

**Exit criteria**:
- Swish and card journeys approved
- Internal payment lifecycle documented
- Swedish/English release gate documented
- Managed translation service shortlist agreed

### Milestone 5 - MVP Build Readiness
**Goal**: Convert approved specs into implementation-ready tasks for the first application slices.

**Exit criteria**:
- Priority user stories decomposed into implementation tasks
- Testing strategy linked to each story
- Operational and compliance sign-off criteria documented

## Traceability Strategy

- Every epic must link back to one or more functional requirements in the spec.
- Every milestone must produce approved artifacts before downstream implementation starts.
- Future implementation tasks must cite concrete repository paths and identify the intended validation layer.

## Open Decisions for Follow-Up

- Confirm whether card payments should stay PSP-neutral in the first implementation milestone.
- Decide whether MVP LOK submission ends at export plus admin approval or includes direct automated submission where technically possible.
- Confirm the managed translation platform shortlist before integration design begins.
