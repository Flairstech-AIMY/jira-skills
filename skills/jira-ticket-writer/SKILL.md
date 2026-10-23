---
name: jira-ticket-writer
description: Convert rough notes, chat messages, customer requests, technical observations, and partially formed requirements into concise Jira-ready Stories, Tasks, Bugs, or investigation items. Use when the user asks to write, create, rewrite, structure, or clean up a Jira issue, or asks whether something should be a story, task, or bug. Preserve provided facts, links, terminology, urgency, and intent. Do not invent requirements, owners, priorities, estimates, implementation details, or evidence that the user did not provide.
---

# Jira Ticket Writer

Turn messy input into a Jira issue that a product, engineering, QA, or DevOps team can act on immediately.

## Core Rules

- Preserve the user's intent and all confirmed facts.
- Follow `jira-description-format`: open every Description with a short prose narrative of the need and the story behind it (no leading header, never `## Business Context`), and omit `## Suggested Owner`, `## Estimate`, `## Dependencies`, and `## Technical Notes` unless the user explicitly asks for them.
- Keep the ticket concise while retaining the current workflow, concrete difficulty, business reason and examples that explain the need to an engineer.
- Do not invent missing behavior, technical details, dates, severity, assignees, estimates, or acceptance criteria that are not supported by the input.
- Preserve supplied URLs and references exactly unless the user explicitly asks to clean them.
- Prefer testable outcomes over implementation instructions.
- Keep terminology consistent with the user's product names and domain language.
- Make urgency visible when the user explicitly states it, but do not assign a Jira priority unless asked.
- If missing product intent affects the feature, ask or flag it for the user outside the publishable description. If the user has delegated a method to research, preserve the outcome and investigate the method rather than asking them to design it.
- Do not add sections that contain no useful information.
- When the title will appear on a customer-facing or stakeholder roadmap, make the delivered outcome clear in plain language without relying on internal context or unexplained jargon.
- Keep the Jira Summary and Description separate: never repeat the issue title as an H1 or first line in the Description. Begin with the problem narrative.
- Use plain hyphens for authored title separators; avoid em dashes and vertical-bar prose separators. Preserve exact source text when fidelity is required.

## Choose the Issue Type

Use the issue type requested by the user when one is explicitly specified.

Otherwise:

- **Story**: A user, customer, admin, agent, or other actor receives a feature or observable behavior change. An investigation or engineering activity does not become a Story through an `As a user` sentence.
- **Bug**: Existing behavior is incorrect, broken, inconsistent with intended behavior, or has regressed.
- **Task**: Internal technical work, implementation work, maintenance, configuration, migration, cleanup, or a concrete engineering deliverable without a standalone user-value story.
- **Investigation / Spike**: The primary objective is to discover a cause, validate feasibility, or answer an unresolved technical question. Use this only when the Jira project supports such an issue type. Otherwise use a Task and make the investigation objective explicit.

When the user asks whether something is a Story or Task, explain the distinction briefly and select based on the rules above.

## Workflow

1. Identify the requested outcome.
2. Extract only confirmed context, behavior, impact, constraints, examples, and references.
3. Select the issue type.
4. Remove duplicated or low-value information.
5. Structure the ticket using the most appropriate template below.
6. Write Definition of Done bullets that describe observable completion conditions. Use Acceptance Criteria when explicitly requested.
7. Check that every completion condition is supported by the stated requirement, including whether examples are illustrative or fixed rules.
8. Check that no supplied reference or important edge case was lost.
9. Verify the Description does not repeat the Jira Summary/title.

## Story Format

Use this structure when the issue is a Story. Omit optional sections when unnecessary.

```markdown
[Opening narrative: who needs the feature, what happens today, their concrete difficulty, and the outcome they expect.]

## Definition of Done
- [Observable, testable result]
- [Observable, testable result]

## Examples
[Only include scenarios that materially clarify the behavior.]

## References
- [Provided reference]
```

Do not force an `As a / I want / so that` sentence when it would be artificial. If the work has only an internal engineering deliverable or investigation decision, use the appropriate Task or Research type instead of disguising it as a Story.

## Task Format

```markdown
[Opening narrative: the problem, why this work is needed and the concrete technical or operational outcome.]

## Scope
- [Required work]
- [Required work]

## Definition of Done
- [Observable completion condition]
- [Observable completion condition]

## References
- [Provided reference]
```

## Bug Format

```markdown
[Opening narrative: the observed defect, affected workflow and supplied evidence of its impact.]

## Impact
[Who or what is affected, using only provided information.]

## Actual Behavior
[What currently happens.]

## Expected Behavior
[What should happen.]

## Reproduction / Conditions
[Known trigger, environment, sequence, or conditions. Omit if unknown.]

## Evidence
[Logs, screenshots, IDs, links, examples, timestamps, or other supplied evidence.]

## Definition of Done
- [The defect no longer occurs under the known condition.]
- [Expected behavior is verified.]

## References
- [Provided reference]
```

## Completion Conditions

Write Definition of Done bullets, or Acceptance Criteria when requested, that are:

- observable;
- testable;
- tied directly to the requirement;
- concise;
- free of invented thresholds or technical design choices.

Prefer:

`When a contact has multiple profiles with different names, AiMY asks the caller to identify themselves before selecting a profile.`

Avoid:

`Implement robust profile detection with best practices.`

## Style

- Lead with the actual work or user problem.
- Prefer short sections and bullets.
- Avoid generic phrases such as `improve the user experience` unless the concrete improvement is also stated.
- Avoid unnecessary introductions and conclusions.
- Avoid repeating the same requirement in Problem, Requirements, and Acceptance Criteria with identical wording.
- Keep useful examples because they often remove ambiguity faster than more prose.
- Keep future enhancements separate from current scope when the user distinguishes them.
- Make related roadmap titles describe distinct customer outcomes rather than implementation subtasks.
- In a review artifact, keep assignment reminders, local draft codes and questions for the reviewer separate. Before Jira publication, replace draft references with verified issue links and remove review-only notes.
- Incorporate user answers into the narrative and completion conditions, then remove answered review flags. Keep unapproved suggestions distinguishable from confirmed requirements.

## Final Quality Check

Before returning the ticket, verify:

- The issue type matches the nature of the work.
- The title describes the outcome or defect, not the conversation about it, and is understandable to its roadmap audience.
- The problem and scope are understandable without the original chat.
- No unsupported assumptions were introduced.
- Completion conditions are testable.
- Important examples and references remain intact.
- The Jira Description starts with useful content rather than a duplicate title.
- The result is ready to paste into Jira.
