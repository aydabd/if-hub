# Tasks: Platform Foundation and Club Operations MVP

**Input**: Design documents from `specs/001-platform-foundation/`
**Prerequisites**: `spec.md`, `plan.md`

**Tests**: Validation in this first PR is documentation and consistency review; implementation tests will be added in follow-up epics.

**Organization**: Tasks are grouped by epic-aligned user story outcomes so backlog planning can proceed incrementally.

## Phase 1: Setup (Shared Infrastructure)

- [x] T001 Initialize spec-kit in the repository root
- [x] T002 Populate `.specify/memory/constitution.md` with project-specific governance
- [x] T003 Add baseline specification and plan artifacts under `specs/001-platform-foundation/`
- [x] T004 Add issue templates for epic and user story tracking in `.github/ISSUE_TEMPLATE/`
- [x] T005 Add milestone roadmap documentation in `specs/backlog/milestones.md`

---

## Phase 2: Foundational Backlog Alignment

- [ ] T006 Review and approve milestone scope with product stakeholders
- [ ] T007 Map each functional requirement in `spec.md` to an owning epic and milestone
- [ ] T008 Confirm unresolved decisions in `plan.md` for card PSP strategy, LOK submission depth, and translation platform choice

**Checkpoint**: Governance and backlog structure are approved for implementation planning.

---

## Phase 3: User Story 1 - Establish a compliant product baseline (Priority: P1) 🎯 MVP

**Goal**: Make the repo ready for disciplined, spec-driven product delivery.

**Independent Test**: A reviewer can trace constitution -> spec -> plan -> tasks -> issue templates -> milestone roadmap without missing artifacts.

- [ ] T009 [US1] Review spec-kit prompts and align them with the approved constitution as future iterations require
- [ ] T010 [US1] Create the first GitHub epic issues using `.github/ISSUE_TEMPLATE/epic.yml`
- [ ] T011 [US1] Create the first GitHub user story issues using `.github/ISSUE_TEMPLATE/user_story.yml`
- [ ] T012 [US1] Create repository milestones that match `specs/backlog/milestones.md`

---

## Phase 4: User Story 2 - Let coaches focus on attendance while LOK runs in the background (Priority: P1)

**Goal**: Prepare the next spec slice for attendance and LOK automation.

**Independent Test**: The team can describe the attendance-to-LOK flow, failure handling, and audit expectations without implementation ambiguity.

- [ ] T013 [US2] Author a dedicated attendance and LOK feature spec under `specs/002-attendance-lok/`
- [ ] T014 [US2] Define key entities and acceptance scenarios for attendance, evaluation, export, and submission retry behavior
- [ ] T015 [US2] Identify the required validation layers for attendance and LOK workflows

---

## Phase 5: User Story 3 - Support Swedish eID from day one with room to extend (Priority: P1)

**Goal**: Prepare the next spec slice for identity and access.

**Independent Test**: The team can name the provider contract, lifecycle states, and onboarding/linking scenarios for BankID and Freja+.

- [ ] T016 [US3] Author a dedicated identity feature spec under `specs/003-identity-foundation/`
- [ ] T017 [US3] Define entities and workflows for users, people, providers, and verification sessions
- [ ] T018 [US3] Capture compliance and operational review needs for identity integrations

---

## Phase 6: User Story 4 - Accept payments through Swedish-first rails (Priority: P2)

**Goal**: Prepare the next spec slice for Swish and card payments.

**Independent Test**: The team can explain how payment intents, callbacks, and reconciliation behave across providers.

- [ ] T019 [US4] Author a dedicated payments feature spec under `specs/004-payments/`
- [ ] T020 [US4] Define the internal payment status lifecycle and reconciliation rules
- [ ] T021 [US4] Document provider onboarding criteria and webhook/idempotency expectations

---

## Phase 7: User Story 5 - Ship a fully bilingual MVP (Priority: P2)

**Goal**: Prepare the next spec slice for localization and translation operations.

**Independent Test**: The team can explain how translation source files, review workflows, and release gates work for Swedish and English.

- [ ] T022 [US5] Author a dedicated localization feature spec under `specs/005-localization/`
- [ ] T023 [US5] Define repository ownership of localization source files and managed translation sync expectations
- [ ] T024 [US5] Document bilingual release checks and fallback rules for missing translations

---

## Final Phase: Polish & Cross-Cutting Concerns

- [ ] T025 Cross-check all roadmap artifacts for consistency after stakeholder review
- [ ] T026 Update contributor guidance if the approved spec-kit workflow changes
- [ ] T027 Re-run repository validation after backlog artifacts stabilize
