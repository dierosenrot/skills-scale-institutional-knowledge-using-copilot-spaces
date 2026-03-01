# Release Checklist

> **Owner:** Release Coordinator  
> **Stakeholders:** Project Manager, QA Lead, Developers, DevOps/Operations, Project Sponsor  
> **Reference:** [Roles and Personas](../octoacme-roles-and-personas.md) · [Release & Deployment Guide](../octoacme-release-and-deployment.md)

Use this checklist for every release. Complete all items in each phase before proceeding to the next. If a blocker is found, document it in the release ticket and escalate per the [escalation path](#escalation-path).

---

## Pre-Release Phase

### Coordination
- [ ] Release date and deployment window confirmed with DevOps/Operations.
- [ ] Feature freeze communicated to all Developers; no further merges to the release branch without Release Coordinator approval.
- [ ] All planned pull requests merged and CI pipeline green on the release branch.
- [ ] Release ticket created in the project tracker with links to this checklist and the release branch.

### Quality Gates
- [ ] QA Lead has signed off on the release candidate (see [QA Checklist](qa-checklist.md)).
- [ ] All release-blocking defects resolved or formally deferred with written PM approval.
- [ ] Security scan completed; no new critical or high vulnerabilities introduced.
- [ ] Performance benchmarks verified (if applicable).

### Documentation & Communication
- [ ] Release notes drafted, reviewed, and approved by Product Manager.
- [ ] Internal changelog updated.
- [ ] Stakeholder notification drafted (email/Slack) and approved by Change Champion or PM.
- [ ] Support team briefed on known issues and FAQ updates.

### Rollback Planning
- [ ] Rollback procedure documented and linked in the release ticket.
- [ ] Rollback tested in a staging environment (or risk accepted and documented).
- [ ] On-call schedule confirmed; incident escalation contacts up to date.
- [ ] Database migration rollback scripts prepared (if applicable).

### Sign-offs
- [ ] Project Manager acknowledges go-ahead.
- [ ] Project Sponsor sign-off obtained for major releases (v+1.0 or higher).
- [ ] Release Coordinator confirms all pre-release items are complete.

---

## Release Window Phase

### Deployment Steps
- [ ] Deployment window officially opened; stakeholders notified.
- [ ] Pre-deployment backup or snapshot taken (if applicable).
- [ ] Deployment to staging environment completed.
- [ ] Smoke tests executed against staging; results recorded.
- [ ] Deployment to production initiated via automated pipeline (preferred) or manual steps per runbook.
- [ ] Deployment completion confirmed by DevOps/Operations.

### Immediate Verification
- [ ] Critical user flows smoke-tested in production.
- [ ] Monitoring dashboards checked for anomalies (error rate, latency, availability).
- [ ] Integration touchpoints verified (APIs, third-party services, etc.).
- [ ] No P1/P2 incidents triggered within the first 15 minutes post-deployment.

### Communication
- [ ] "Deployment complete" status sent to stakeholders.
- [ ] Release notes published (internal wiki, product changelog, etc.).
- [ ] Customer-facing announcement sent (if applicable).

---

## Post-Release Phase

### Verification & Monitoring
- [ ] Extended monitoring window observed (minimum 24 hours for minor releases, 48 hours for major).
- [ ] Support ticket queue monitored for release-related issues.
- [ ] Metrics reviewed: user adoption, error rates, key product KPIs.

### Incident Handling (if applicable)
- [ ] Any incidents triaged and P1 hotfixes initiated within SLA.
- [ ] Incident post-mortem scheduled (if P1/P2 occurred).
- [ ] Rollback executed and documented if production stability was impacted.

### Closure
- [ ] Release ticket updated with final status (success, partial, rolled back).
- [ ] Outstanding deferred defects re-triaged and scheduled.
- [ ] Release retrospective items captured and assigned (see [Retrospective Guide](../octoacme-retrospective-and-continuous-improvement.md)).
- [ ] This checklist archived with the release ticket for audit purposes.

---

## Escalation Path

| Situation | Escalate To | Method |
|---|---|---|
| QA hold — blocking defect | QA Lead → PM → Project Sponsor | Release ticket comment + Slack/email |
| Deployment failure | DevOps On-Call → Release Coordinator → PM | Incident channel + phone |
| Rollback decision | Release Coordinator + PM | Synchronous call; document outcome |
| Release delay (> 2 hours) | PM → Project Sponsor | Email + status update in release ticket |
| Critical security vulnerability found | PM + Security team | Immediate; do not deploy |
