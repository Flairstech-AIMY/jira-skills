---
name: jira-product-owner
description: Turn product requirements into clear Jira stories, tasks, bugs, research items, and epics, and help plan Jira work or write Jira ticket files. Use for general product ownership and ticket planning; use the focused Jira skills for conversational AI behavior, production incidents, ticket refinement, ticket drafting, or detailed feature breakdowns.
---

# Jira Product Owner

Translate raw requirements into actionable Jira work that makes the business value, intended user, workflow, and expected outcome clear. Preserve the original intent; do not invent requirements, stakeholders, dates, estimates, project settings, or implementation decisions.

For specialized conversational AI behavior, production incidents, ticket refinement, ticket drafting, or detailed feature-to-story breakdowns, use the corresponding focused skill when available.

For rough notes covering several initiatives, use `jira-feature-breakdown` when available: understand the needs, group Epics, define user features, identify research decisions, then add only necessary technical Tasks. Use `jira-research-task` for investigations that need clear questions, evidence and decision outputs.

## Choose the work item type

- **Epic:** a multi-sprint initiative that needs coordinated work.
- **Story:** a feature a user receives and can demonstrate. An engineering activity does not become a Story by adding an `As a user` sentence.
- **Task:** necessary technical work that is not itself a user story.
- **Bug:** behavior that is broken or differs from the expected result.
- **Research:** a bounded investigation that answers a specific decision with evidence; do not invent a timebox or treat investigation as feature delivery.
- Use project-supported types for design, infrastructure, or other specialized work when relevant.

## Titles

For stories and other outcome-focused tickets, use:

`{Product / Initiative} - {Domain / Area} - {User-Facing Outcome}`

Describe what the user or stakeholder can accomplish. Keep implementation discipline and role tags (such as Frontend, Backend, Infrastructure, or Research) out of the title; mention an owner only when the user asks for one. For work that is inherently non-user-facing, retain the same clear product/domain framing and state the deliverable rather than pretending it is a user feature.

When titles will appear on a customer-facing or stakeholder roadmap, use plain language that makes the delivered outcome understandable without the original conversation or internal project context. Avoid unexplained acronyms, implementation terms, and internal workflow labels. Keep related titles distinct enough that a reader can tell what each delivers.

## Jira Description formatting

The Jira Summary is the issue title; the Description is separate content. Do not repeat the Summary as a Markdown H1 or as the first line of the Description. Start the Description with a short prose narrative of the need and the story behind the user's expectation, not with a header such as `## Business Context`. Never include `## Suggested Owner`, `## Estimate`, `## Dependencies`, or `## Technical Notes` unless the user explicitly asks for them. Apply the same rule when creating or updating any issue type.

## Story body

Use this structure for stories:

```markdown
{Opening prose, no header: the user need, the idea behind the expectation, the workflow or problem, and the business value, told as a short story.}

## Definition of Done
- List the observable outcomes required for completion.
```

Add `## Technical Notes`, `## Suggested Owner`, `## Estimate`, or `## Dependencies` only when the user explicitly requests that information. Do not add Acceptance Criteria unless the user explicitly asks for them. Keep the Definition of Done concise and verifiable; do not restate the entire implementation plan. For other issue types, adapt the sections to the work while retaining a clear context, purpose, and completion outcome.

## Break down larger initiatives

Split larger initiatives by independently demonstrable user outcomes. Keep a meaningful end-to-end workflow together, and separate research when a decision is unresolved. Keep technical Tasks minimal; engineers can choose the implementation breakdown and propose further Stories after research. Do not manufacture frontend, backend, UX or infrastructure Stories to cover engineering layers, or claim sprint-sized delivery without a known scope.

When a workflow has distinct user-visible stages (for example, handling a request, guiding the user through an eligible step, explaining follow-up, and preparing a handoff), assign each requirement to one clear ticket. Split only where the outcome can be delivered and validated independently; do not repeat shared behavior across several tickets.

When rewriting or mapping existing Jira work, preserve its intent and provide a traceable old-to-new mapping. Cover the full workflow that the user actually described; do not impose a generic workflow where it does not apply.

Give the engineer the current workflow, the concrete difficulty, why the change matters, confirmed expectations and useful examples. Keep examples configurable or illustrative when the user says they are examples. Put questions for the reviewing user outside publishable issue content, and remove answered flags when incorporating their decisions.

## Before creating Jira issues

Resolve the target project and required create fields before creation. Reuse project, board, sprint, priority, relationship and stakeholder decisions already supplied in the session, including permission to leave optional fields unset. Ask only for still-missing information that materially affects the requested action. Do not invent values, repeatedly reopen answered intake questions, or hardcode a project from a previous engagement. Intake need not block drafting.

Before creating, search and read plausible existing matches. Compare actor, trigger, outcome and delivery scope; classify duplicate, partial overlap, related work, prior design/research, or unrelated. A design Task in UAT is not evidence that its runtime feature has shipped. Apply user corrections to matches and do not reintroduce rejected references without new evidence. If the choice to update or create remains material and unauthorized, present the reconciliation for review.

When updating or creating issues, use the exact configured Jira values for parent, sprint, and fix version. Validate the available option/name rather than assuming a shorthand version string is accepted; preserve existing relationships and fields unless the user asks to change them.

Use the available Jira integration when the user requests an issue to be created or updated. Check relevant project/type/field requirements and available tool documentation first. Confirm the resulting issue key and link only after the operation succeeds.

When the user is reviewing before creation, preserve that boundary and prepare a concrete review artifact when requested. When creation is already authorized, do not add another approval step solely because this skill is being used. Keep local review codes and assignment notes out of Jira descriptions; resolve references to real issue links. For an instruction such as "add transcription and change nothing else," edit only the requested content and verify it by reading the issue back, without unrelated formatting cleanup.

## Ticket files

When asked to produce Markdown files, follow the requested destination and naming convention. If the project specifies a `tickets/` directory with one subfolder per session, follow that convention and name each file from its ticket title. Do not create files in unrequested locations. A standalone ticket file may include its title; omit that heading when the content is intended for the Jira Description field.

## Quality check

Before returning a ticket, verify that it:

- States a specific user or stakeholder need and why it matters.
- Defines a clear outcome and a concise, observable Definition of Done.
- Uses an outcome-focused title without role tags and, when roadmap-facing, plain language a customer can understand.
- Contains no duplicate title in the Jira Description.
- Opens with a prose narrative (no header) and has no Suggested Owner, Estimate, Dependencies, or Technical Notes sections unless requested.
- Is appropriately sized and independently deliverable, or has explicit dependencies.
- Contains only necessary technical guidance and no invented facts.
- Omits Acceptance Criteria unless requested.
