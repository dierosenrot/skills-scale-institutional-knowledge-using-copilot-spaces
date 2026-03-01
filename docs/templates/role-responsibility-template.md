# Role Responsibility Template

Use this template when proposing a new role or persona for OctoAcme projects. Copy the entire file, fill in each section, and open a pull request that updates [octoacme-roles-and-personas.md](../octoacme-roles-and-personas.md).

> **Instructions:** Replace every `[placeholder]` with the appropriate content. Delete any guidance notes (lines beginning with `>`) before merging.

---

## Role Name

`[Role Name]`

> Provide the official title used consistently across project documentation and tooling (e.g., JIRA, Confluence, GitHub).

---

## Purpose

`[One or two sentences describing why this role exists and the primary value it delivers to the project.]`

---

## Responsibilities

> List the key responsibilities in order of priority. Aim for 5–10 items. Each item should be a concrete, observable activity.

- [ ] `[Responsibility 1]`
- [ ] `[Responsibility 2]`
- [ ] `[Responsibility 3]`
- [ ] `[Responsibility 4]`
- [ ] `[Responsibility 5]`

---

## Decision Rights

> Describe what this role is empowered to decide independently, what requires consultation, and what must be escalated. For each row, select **one** authority level (Independent, Consult, or Escalate) and delete the others.

| Decision | Authority Level | Notes |
|---|---|---|
| `[Decision 1]` | `[Independent \| Consult \| Escalate]` | `[Notes]` |
| `[Decision 2]` | `[Independent \| Consult \| Escalate]` | `[Notes]` |
| `[Decision 3]` | `[Independent \| Consult \| Escalate]` | `[Notes]` |

---

## Interactions

> List the roles this persona interacts with most frequently and describe the nature of each interaction.

| Role | Interaction Type | Frequency | Description |
|---|---|---|---|
| `[Role A]` | Inform / Consult / Collaborate / Escalate | Daily / Weekly / As needed | `[Brief description of what is exchanged or decided]` |
| `[Role B]` | Inform / Consult / Collaborate / Escalate | Daily / Weekly / As needed | `[Brief description]` |
| `[Role C]` | Inform / Consult / Collaborate / Escalate | Daily / Weekly / As needed | `[Brief description]` |

---

## RACI Matrix Entry

> Add rows for the key activities this role participates in. Use: **R** = Responsible, **A** = Accountable, **C** = Consulted, **I** = Informed.

| Activity | `[This Role]` | PM | PdM | `[Other Role 1]` | `[Other Role 2]` |
|---|---|---|---|---|---|
| `[Activity 1]` | R/A/C/I | R/A/C/I | R/A/C/I | R/A/C/I | R/A/C/I |
| `[Activity 2]` | R/A/C/I | R/A/C/I | R/A/C/I | R/A/C/I | R/A/C/I |
| `[Activity 3]` | R/A/C/I | R/A/C/I | R/A/C/I | R/A/C/I | R/A/C/I |

---

## Artifacts Owned

> List documents, reports, dashboards, or deliverables that this role is primarily responsible for creating or maintaining.

- `[Artifact 1]` — `[brief description]`
- `[Artifact 2]` — `[brief description]`
- `[Artifact 3]` — `[brief description]`

---

## Example Tasks

> Provide 3–5 concrete, day-in-the-life examples that illustrate what this role does in practice.

1. `[Example task 1]`
2. `[Example task 2]`
3. `[Example task 3]`

---

## Acceptance Criteria for Documentation Updates

When proposing changes to this role's definition, the pull request must satisfy all of the following:

- [ ] All sections above are filled in completely (no remaining placeholders).
- [ ] The role entry has been added to or updated in [octoacme-roles-and-personas.md](../octoacme-roles-and-personas.md) under an H2 heading.
- [ ] RACI rows have been reviewed against existing personas to avoid unresolved conflicts.
- [ ] At least one team member from the affected area has reviewed and approved the PR.
- [ ] Any open questions have been logged in the "Open Questions / Adoption Notes" section of [octoacme-roles-and-personas.md](../octoacme-roles-and-personas.md).
- [ ] Links to related checklists or templates are included where applicable.
