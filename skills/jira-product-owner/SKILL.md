---
name: jira-product-owner
description: Turn product requirements into clear Jira stories, tasks, bugs, research items, epics, ticket rewrites, and initiative breakdowns. Use when planning or creating Jira work or writing Jira ticket files.
---

# Jira Product Owner

Translate raw requirements into actionable Jira work that makes the business value, intended user, workflow, and expected outcome clear. Preserve the original intent; do not invent requirements, stakeholders, dates, estimates, project settings, or implementation decisions.

## Choose the work item type

- **Epic:** a multi-sprint initiative that needs coordinated work.
- **Story:** a user-facing capability or outcome.
- **Task:** necessary technical work that is not itself a user story.
- **Bug:** behavior that is broken or differs from the expected result.
- **Research:** a time-bounded investigation that answers a specific question.
- Use project-supported types for design, infrastructure, or other specialized work when relevant.

## Titles

For stories and other outcome-focused tickets, use:

`{Product / Initiative} – {Domain / Area} – {User-Facing Outcome}`

Describe what the user or stakeholder can accomplish. Keep implementation discipline and role tags (such as Frontend, Backend, Infrastructure, or Research) out of the title; put a suggested owner in the body when known. For work that is inherently non-user-facing, retain the same clear product/domain framing and state the deliverable rather than pretending it is a user feature.

## Story body

Use this structure for stories:

```markdown
# {Product / Initiative} – {Domain / Area} – {User-Facing Outcome}

## Business Context
Explain the user need, workflow, problem, and business value.

## Purpose
State the user-facing goal and expected outcome.

## Technical Notes
Include only information necessary to clarify delivery or important constraints.

## Definition of Done
- List the observable outcomes required for completion.

## Suggested Owner
{Accountable person or team, if known; otherwise TBC}

## Estimate
{S / M / L, or the requested estimate scale}
```

Do not add Acceptance Criteria unless the user explicitly asks for them. Keep the Definition of Done concise and verifiable; do not restate the entire implementation plan. For other issue types, adapt the sections to the work while retaining a clear context, purpose, and completion outcome.

## Break down larger initiatives

Split multi-sprint work into independently deliverable tickets that can be completed within a sprint. Depending on the actual workflow, consider separate work for user experience, frontend, backend/file and history management, orchestration or analysis flow, research, integrations, data collection, and storage/security/infrastructure. Use only the areas required by the initiative; do not create filler tickets. Preserve dependencies and make blockers explicit.

When rewriting or mapping existing Jira work, preserve its intent and provide a traceable old-to-new mapping. Cover the full workflow that the user actually described; do not impose a generic workflow where it does not apply.

## Before creating Jira issues

If the user has not already provided these details, ask for the missing information before creating issues: Jira project/board, sprint, priority, dependencies, blockers, and stakeholders. Do not guess issue types, issue fields, owners, or relationships. If some details are not applicable, confirm or document that rather than fabricating values. This intake requirement applies to issue creation; it need not block drafting a proposed ticket when the user only asks for text or a file.

Use the available Jira integration when the user requests an issue to be created or updated. Check relevant project/type/field requirements and available tool documentation first. Confirm the resulting issue key and link only after the operation succeeds.

## Ticket files

When asked to produce Markdown files, follow the requested destination and naming convention. If the project specifies a `tickets/` directory with one subfolder per session, follow that convention and name each file from its ticket title. Do not create files in unrequested locations.

## Quality check

Before returning a ticket, verify that it:

- States a specific user or stakeholder need and why it matters.
- Defines a clear outcome and a concise, observable Definition of Done.
- Uses an outcome-focused title without role tags.
- Is appropriately sized and independently deliverable, or has explicit dependencies.
- Contains only necessary technical guidance and no invented facts.
- Omits Acceptance Criteria unless requested.
