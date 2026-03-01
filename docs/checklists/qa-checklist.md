# QA Readiness Checklist

> **Owner:** QA Lead  
> **Stakeholders:** Developers, Release Coordinator, Product Manager, Project Manager  
> **Reference:** [Roles and Personas](../octoacme-roles-and-personas.md) · [Release Checklist](release-checklist.md)

Use this checklist before issuing a QA sign-off for a release candidate. All items must be checked (or explicitly waived with written justification) before the QA Lead communicates go/no-go to the Release Coordinator.

---

## Test Planning

- [ ] Test plan created and approved for the current milestone/release.
- [ ] Acceptance criteria reviewed for all user stories included in the release.
- [ ] Test cases written and linked to acceptance criteria in the project tracker.
- [ ] Regression suite updated to reflect new functionality.
- [ ] Test environments provisioned and verified to match production configuration.
- [ ] Test data prepared (anonymized/synthetic where required by data-handling policy).

---

## Test Coverage

- [ ] All acceptance criteria have at least one corresponding test case.
- [ ] Code coverage meets or exceeds the project's defined threshold (see project standards doc for threshold, e.g., 80%).
- [ ] Edge cases and negative test scenarios identified and covered.
- [ ] Integration tests cover all external system touchpoints affected by this release.
- [ ] API contract tests executed (if applicable).
- [ ] Accessibility tests executed for any UI changes (if applicable).

---

## Test Execution

- [ ] Full regression suite executed on the release candidate build.
- [ ] Smoke tests executed in the staging environment.
- [ ] All P1 (critical) and P2 (high) defects resolved and re-verified.
- [ ] P3 / P4 defects triaged; open items documented with PM/PdM acceptance.
- [ ] No new defects introduced since last QA cycle (or delta documented).
- [ ] Exploratory testing completed for high-risk areas.

---

## Performance & Security

- [ ] Load/performance tests executed (if applicable) and results within acceptable thresholds.
- [ ] Security scan (SAST/DAST) run on the release candidate; no new critical or high findings.
- [ ] Dependency vulnerability scan completed; findings addressed or risk-accepted in writing.

---

## Test Environments

- [ ] Staging environment reflects production configuration (versions, infra, data volumes).
- [ ] Environment health verified prior to test execution (no pre-existing issues that could skew results).
- [ ] Test environment cleaned up after test execution to prevent data bleed between runs.
- [ ] Production-like data volumes tested (if performance is a concern).

---

## Acceptance Criteria Verification

- [ ] Product Manager (or delegate) has reviewed and confirmed all user-story acceptance criteria are met.
- [ ] Definition of Done reviewed; all items satisfied for stories in scope.
- [ ] UAT (User Acceptance Testing) completed and signed off by appropriate stakeholder (if required).
- [ ] Release notes reviewed for technical accuracy by QA Lead.

---

## QA Sign-off

Complete this section last. The QA Lead must complete all items above (or document waivers) before signing off.

- [ ] All checklist items above are complete or formally waived with documented justification.
- [ ] QA summary report prepared and shared with Release Coordinator and PM.
- [ ] Open defect list reviewed with PM; agreement reached on deferral decisions.
- [ ] **QA Lead sign-off recorded:** `[Name]` on `[Date]` — Status: ✅ Go / 🚫 No-Go

> If **No-Go**: document the blocking reason(s) in the release ticket and notify the Release Coordinator immediately.

---

## Waiver Log

Use this table to record any checklist items that are intentionally skipped with justification and approver sign-off.

| Checklist Item | Justification | Approved By | Date |
|---|---|---|---|
| `[Item]` | `[Reason]` | `[Name / Role]` | `[Date]` |
