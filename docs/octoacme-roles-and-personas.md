# OctoAcme Roles and Personas

> **Related documents:** [Project Management Overview](octoacme-project-management-overview.md) · [Role Responsibility Template](templates/role-responsibility-template.md)

## How to use this document

This document defines every recognized role and persona within OctoAcme projects. Use it to:

- **Onboard** new team members by pointing them to the persona that matches their function.
- **Add a new persona** by copying the [Role Responsibility Template](templates/role-responsibility-template.md), filling in all sections, and opening a pull request against this file.
- **Map responsibilities** by reviewing the RACI tables in each persona section and the cross-cutting RACI summary at the end of this document.
- **Link to a specific persona** using the anchor links in the table of contents below (e.g., `[Release Coordinator](#release-coordinator)`).

When a new role is proposed, check the [Role Responsibility Template](templates/role-responsibility-template.md) for the minimum required fields and ensure alignment with the existing personas before merging.

---

## Table of Contents

- [Project Sponsor](#project-sponsor)
- [Release Coordinator](#release-coordinator)
- [QA Lead](#qa-lead)
- [Change Champion](#change-champion)
- [Cross-Cutting RACI Summary](#cross-cutting-raci-summary)
- [Open Questions / Adoption Notes](#open-questions--adoption-notes)

---

## Project Sponsor

**Purpose:** Ensure the project aligns with organizational strategy, secure executive-level resources and budget, and serve as the primary escalation point for decisions beyond the Project Manager's authority.

**Key responsibilities:**
- Champion the project at the executive or steering-committee level.
- Approve project charter, major scope changes, and budget adjustments.
- Remove organizational blockers escalated by the Project Manager.
- Review and sign off on milestone completions and go/no-go release decisions.
- Monitor overall project health and intervene when strategic risks emerge.

**Typical interactions with existing roles:**
- **Project Manager (PM):** Weekly or bi-weekly status briefings; PM escalates blockers and risks; Sponsor provides decisions and resource commitments.
- **Product Manager (PdM):** Aligns on product vision, validates strategic fit of major features or pivots.
- **Steering Committee / Executives:** Represents the project's progress and needs; surfaces key decisions for approval.
- **Change Champion:** Provides organizational authority to support change-management activities; approves communication plans.

**Decision authority:**
- Final approval on scope increases that impact budget or timeline beyond defined thresholds.
- Go/no-go authority for major releases in the absence of a delegated decision-maker.
- Resolution of cross-team conflicts when PM escalation is insufficient.

**Example tasks:**
- Review and sign the Project Charter during initiation.
- Approve addition of a new workstream mid-project.
- Attend quarterly steering committee to present project status.
- Co-author executive announcement for a major product release.

**RACI:**

| Activity | Project Sponsor | PM | PdM | Release Coordinator | QA Lead | Change Champion |
|---|---|---|---|---|---|---|
| Project Charter sign-off | **A** | R | C | — | — | I |
| Release go/no-go decision | **A** | R | C | C | C | I |
| Risk escalation (critical) | **A** | R | I | I | I | I |
| Change adoption approval | **A** | C | C | I | I | R |

---

## Release Coordinator

**Purpose:** Orchestrate all activities required for a safe, timely, and well-communicated deployment, from scheduling through post-release verification.

**Key responsibilities:**
- Maintain the release calendar and communicate deployment windows to all stakeholders.
- Confirm readiness gates (CI green, QA sign-off, rollback plan documented) before each release.
- Coordinate with Development, QA, and DevOps/Operations to sequence deployment steps.
- Draft and distribute release notes and stakeholder communications.
- Track post-release incidents and ensure hotfixes are triaged within SLA.
- Own the [Release Checklist](checklists/release-checklist.md) and ensure it is completed for every release.

**Typical interactions with existing roles:**
- **QA Lead:** Receives QA sign-off or hold; coordinates on test environment availability and last-minute defect triage.
- **Developers:** Confirms feature-freeze dates, merge deadlines, and build artifact availability.
- **DevOps/Operations:** Aligns on deployment pipeline, environment configs, and rollback procedures.
- **Project Manager:** Reports release status, escalates blocking issues.
- **Project Sponsor:** Requests go/no-go sign-off for major releases.
- **Change Champion:** Shares stakeholder communication drafts for review before distribution.

**Decision authority:**
- Can delay a release when readiness gates are not met (escalate to PM/Sponsor for major delays).
- Approves the final deployment schedule within a given sprint or cycle.

**Example tasks:**
- Create a release ticket with checklist items linked to the [Release Checklist](checklists/release-checklist.md).
- Run the pre-release readiness call with QA Lead and DevOps.
- Send the release announcement email and update the changelog.
- Conduct a post-release retrospective item capture within 48 hours.

**RACI:**

| Activity | Release Coordinator | PM | QA Lead | Developers | DevOps | Project Sponsor |
|---|---|---|---|---|---|---|
| Release schedule creation | **R** | A | C | C | C | I |
| Pre-release readiness gate | **R/A** | I | C | C | C | I |
| Deployment execution | C | I | I | R | **A** | I |
| Release communication | **R** | A | I | I | I | C |
| Post-release verification | **R** | I | C | C | C | I |

---

## QA Lead

**Purpose:** Define and drive the quality assurance strategy, ensure all deliverables meet acceptance criteria, and provide a clear quality signal before each release.

**Key responsibilities:**
- Author and maintain the test strategy and test plans for each milestone.
- Oversee execution of functional, regression, integration, and acceptance tests.
- Coordinate defect triage with Developers and track resolution to closure.
- Provide a formal QA sign-off or hold decision to the Release Coordinator.
- Continuously improve QA tooling, coverage metrics, and processes.
- Own the [QA Checklist](checklists/qa-checklist.md) and verify it is completed before sign-off.

**Typical interactions with existing roles:**
- **Developers:** Daily collaboration on defect reproduction, fix verification, and test automation contributions.
- **Release Coordinator:** Delivers QA sign-off report; escalates blocking defects that threaten the release window.
- **Product Manager (PdM):** Aligns acceptance criteria to test cases; clarifies expected behavior for edge cases.
- **Project Manager:** Reports test coverage, open defects, and risk to schedule.
- **Change Champion:** Provides quality metrics and test results to support change communications.

**Decision authority:**
- Issues the QA sign-off (or hold) that gates deployment.
- Prioritizes defect severity and determines whether a defect is a release blocker.

**Example tasks:**
- Write test cases for new feature acceptance criteria in the project tracker.
- Execute the [QA Checklist](checklists/qa-checklist.md) before each release candidate.
- Facilitate a defect triage meeting with Developers.
- Publish a QA summary report for the release retrospective.

**RACI:**

| Activity | QA Lead | Developers | Release Coordinator | PM | PdM |
|---|---|---|---|---|---|
| Test strategy definition | **R/A** | C | I | I | C |
| Test execution | **R** | C | I | I | I |
| Defect triage | **R/A** | R | C | I | C |
| QA sign-off / hold | **A** | I | C | I | I |
| Test coverage reporting | **R** | C | I | A | I |

---

## Change Champion

**Purpose:** Advocate for process and product adoption within the organization, ensure impacted stakeholders are informed and supported, and track change feedback to feed into continuous improvement.

**Key responsibilities:**
- Develop and execute a change-adoption plan for significant project changes or releases.
- Facilitate stakeholder engagement sessions, demos, and training activities.
- Collect and synthesize feedback from business units affected by changes.
- Escalate adoption blockers or resistance to the Project Manager and Project Sponsor.
- Maintain a change-impact log and report adoption metrics at milestone reviews.

**Typical interactions with existing roles:**
- **Project Sponsor:** Receives executive sponsorship messages and co-signs major communications; escalates organizational resistance.
- **Project Manager:** Coordinates on change-communication timelines and resource needs; reports adoption blockers.
- **Product Manager (PdM):** Aligns change narratives with product vision; uses product metrics to measure adoption.
- **Release Coordinator:** Reviews release communications for change-management messaging before distribution.
- **Impacted Business Units:** Primary interface for gathering feedback, running training, and monitoring adoption.

**Decision authority:**
- Approves change-communication content before distribution.
- Recommends go-slow or phased-rollout approaches based on adoption readiness assessment.

**Example tasks:**
- Facilitate a "lunch and learn" demo for a new product feature.
- Draft a change-impact assessment for a process redesign.
- Run a stakeholder survey and summarize results for the PM.
- Update the change-adoption log after each sprint review.

**RACI:**

| Activity | Change Champion | PM | Project Sponsor | PdM | Release Coordinator |
|---|---|---|---|---|---|
| Change-impact assessment | **R/A** | C | I | C | I |
| Stakeholder communication plan | **R** | A | C | C | C |
| Training / enablement | **R/A** | I | I | C | I |
| Adoption metrics reporting | **R** | A | I | C | I |
| Change adoption approval | R | C | **A** | I | I |

---

## Cross-Cutting RACI Summary

The table below summarizes key project activities across all personas defined in this document and the core roles described in the [Project Management Overview](octoacme-project-management-overview.md).

| Activity | Project Sponsor | PM | PdM | Release Coordinator | QA Lead | Change Champion | Developers | DevOps |
|---|---|---|---|---|---|---|---|---|
| Project Charter sign-off | **A** | R | C | — | — | I | — | — |
| Release go/no-go | **A** | R | C | C | C | I | I | I |
| Risk escalation (critical) | **A** | R | I | I | I | I | I | I |
| Release schedule | I | A | C | **R** | C | I | C | C |
| QA sign-off | I | I | C | C | **A** | I | I | I |
| Stakeholder communication | C | A | C | R | I | **R** | I | I |
| Change adoption approval | **A** | C | C | I | I | R | I | I |
| Post-release retrospective | I | **A** | C | R | C | C | C | C |

> **Key:** R = Responsible · A = Accountable · C = Consulted · I = Informed · — = Not involved

---

## Open Questions / Adoption Notes

The items below require stakeholder review before this document is considered final. Please comment on the pull request or open a follow-up issue.

1. **Steering Committee representation:** Should the Project Sponsor section reference a formal Steering Committee charter, or is ad-hoc representation sufficient for current team size?
2. **DevOps persona:** Several RACI rows reference a DevOps/Operations role that is not yet fully defined in this document. A dedicated DevOps persona entry may be needed.
3. **Overlap between Release Coordinator and PM:** Clarify threshold for when the Release Coordinator can approve a delay independently vs. when PM/Sponsor approval is required.
4. **Change Champion allocation:** Determine whether this is a dedicated FTE, a rotated responsibility, or a role assigned per project.
5. **RACI review cadence:** Define how often the RACI tables in this document should be reviewed (suggested: annually or after any major org change).

> @dierosenrot — please review the above open questions and confirm or update before merging.