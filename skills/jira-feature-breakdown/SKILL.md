---
name: jira-feature-breakdown
description: Turn rough notes or a large initiative into Epics, user-facing Stories, focused research and minimal technical Tasks. Use for feature breakdowns, phased delivery, reconciliation with existing Jira work, and reviews of coverage or deliverability. Preserve problem context and engineering freedom, and map review groups to a hierarchy Jira actually supports.
---

# Jira Feature Breakdown

Convert broad product requirements into a clean Jira hierarchy that can be planned and delivered incrementally.

For review artifacts, reconciliation or publication, read [references/review-and-publication.md](references/review-and-publication.md). For ambiguous conversational notes or repeated user corrections, use the examples in [references/review-examples.md](references/review-examples.md). These examples illustrate decisions, not product defaults.

## Core Principles

- Split by user-visible or business capability, not by engineering layer.
- A Story is a feature the user receives and can demonstrate. Researching, designing or implementing a mechanism is not itself a user Story.
- Keep supporting implementation work associated with the feature it enables. Validate whether the project uses sibling Tasks with links or actual child Subtasks; do not assume a Task can have a Story as its Jira parent.
- Create a separate Story only when the capability has independent product value or can be accepted independently.
- Avoid duplicate scope across stories.
- Preserve explicit sprint constraints and phased delivery boundaries.
- Separate current scope from future enhancements.
- Do not invent requirements to make the breakdown look complete.
- Keep technical Tasks minimal. Engineers usually choose the implementation breakdown and may propose further Stories after research.
- When titles are roadmap-facing, use plain customer-understandable language that says what will be delivered; avoid unexplained technical or internal workflow terms.

## Workflow

1. Understand the notes before assigning issue types: extract the current workflow, pain, intended user outcome, constraints, concrete examples and unresolved decisions.
2. Distinguish confirmed requirements, illustrative examples, user-delegated research and unapproved suggestions. Treat the user's later corrections as updates to the affected drafts.
3. Group needs into Epics, then define independently demonstrable user features as Stories.
4. Identify product, technical or UI/UX research decisions that support those features. Research may refine, split or retire a directional Story; it is not a delivered feature.
5. Add only necessary technical Tasks where there is a useful engineering deliverable or an explicitly requested technical change.
6. Reconcile related Jira work by reading plausible matches and comparing actual outcomes, not keywords alone.
7. Trace each source requirement to a retained issue. Merge duplicate outcomes, preserve distinct triggers and workflows, and make intentionally deferred work explicit.
8. Check deliverability, research handoffs and real prerequisites. Avoid making a known useful feature wait for a separable unresolved enhancement.
9. When preparing for Jira, map each issue to a supported parent and each cross-reference to an intended real issue link. Keep review-only notes separate.

## Story Boundary Rules

Create a separate Story when at least one of these is true:

- It introduces a distinct user capability.
- It has different acceptance behavior that can be tested independently.
- It can reasonably ship or be enabled independently.
- It serves a different actor or workflow.
- It represents a separate administration or configuration experience with its own value.

Keep work in the same Story when the split would only represent:

- frontend versus backend;
- UI/UX versus implementation;
- API versus database work;
- one technical layer required to make the same user capability function.

For multi-step conversational support flows, make sure each behavior has one clear home: for example, handling an unavailable transfer, guiding a user through an appropriate action, setting follow-up expectations, and recording a useful teammate handoff. Split only where each behavior has an independently testable outcome, and avoid repeating the same promise or ticket requirement in multiple Stories.

Two drafts with different wording may still describe the same feature. Compare their actor, trigger, capability and acceptance evidence; merge when they do not deliver distinct value. Keep useful examples and references in the retained Story.

## Context and research handoffs

Each Story should explain the user's current difficulty, where it occurs in the workflow, why it matters and the expected feature. Preserve useful anecdotes as concise workflow context. Do not replace the problem with a predetermined button, agent architecture or integration choice when the user has left that choice open.

Use `jira-research-task` when available. Give each investigation a decision boundary, focused questions, evidence to examine, expected outputs and verifiable completion conditions. Link it to the supported feature. Where product and technical investigations meet, state the handoff and avoid circular blocking links.

Ask the user for missing product intent they have not delegated. Put those questions in the review layer, not in prose such as "the notes do not explain this" inside the Story. When the user delegates a method to research, retain the confirmed outcome and let the investigation recommend the method. Incorporate answers into affected drafts and remove answered review flags.

## Deliverability review

- Check that a first delivery completes a useful user journey, including how it starts, the visible result and relevant failure outcomes.
- Separate an independently useful enhancement if its unresolved research would otherwise delay a clear core feature. Do not split a coherent feature simply to create smaller counts.
- Keep foundational capture or retrieval with the outcome it enables when it has no separate user value; allow independent capabilities, such as live chat and a finished meeting record, to be delivered separately.
- Research-dependent Stories can exist in the backlog. Before sprint commitment, incorporate the selected scenarios, boundaries and completion evidence from research.
- Preserve accepted capabilities while recommending sequencing changes. Do not silently drop a confirmed requirement or treat your review suggestion as approved scope.
- When asked only for a review, return supported findings and recommendations without editing the breakdown. It is acceptable to recommend no changes. Avoid manufacturing new work for symmetry.

## Default Output

```markdown
# [Feature / Epic Name]

## Scope Summary
[Short description of the capability and current delivery boundary.]

## Story 1: [Outcome-oriented title]

[Opening narrative: who needs the feature, their current difficulty, useful workflow context and the expected outcome.]

### Requirements
- [Requirement]

### Definition of Done
- [Testable outcome]

### Supporting research or Tasks
[Only investigations or engineering deliverables that are useful to plan now.]

## Story 2: [Outcome-oriented title]
...

## Future Scope
- [Explicitly deferred capability]
```

If the user asks only for Stories, omit Tasks. Add a `### Dependencies` section only when the user asks for dependencies; it must never appear in a Jira Description unless requested.

The headings above organize a standalone planning document. For each actual Description, start with the narrative and use Definition of Done by default; add Acceptance Criteria only when requested.

## Coverage Check

Before returning the breakdown, verify all of the following:

- Every explicit requirement from the source request appears in the breakdown.
- No Story exists solely because a different engineering discipline owns it.
- Each Story has a clear actor or business outcome.
- Tasks are concrete implementation deliverables, not restatements of the Story.
- Dependencies are included only when the user asks for them and a real prerequisite exists.
- Deferred items are not accidentally included in current acceptance criteria.
- Adjacent roadmap titles are distinct, plain-language statements of customer-visible outcomes.

If the user asks whether the current Stories cover the feature, identify missing user capabilities first. Do not manufacture extra Stories merely for symmetry.

## Sprint and Phase Handling

A visual phase grouping must have a deliberate Jira representation. Check the project's issue types, parent fields and available planning fields before publication. Give substantial, independently trackable phases their own Epics when appropriate; use a supported phase field, label or release grouping for smaller stages. Do not prescribe one Epic per phase for every initiative or assume nested Epics are supported.

Keep shared work under one parent and link the phases that use it. State whether an initiative overview is a review grouping or an issue to create, and show the exact proposed parent for every issue. Use blocking links only for real prerequisites; phase numbering alone does not require a serial dependency chain. A phase completion check must account for any required linked capabilities as well as its own child issues.

When the user specifies a limited sprint scope, treat that boundary as authoritative.

For example, if the current sprint supports `1:1`, `1:N`, and `N:1` reconciliation while `N:N` is future work:

- define Stories only for the current supported workflows;
- preserve the shared foundation required by those workflows;
- place `N:N` under future scope unless it requires preparatory work now;
- do not make its acceptance criteria part of the current sprint.

## Style

- Use concise, product-oriented titles.
- Keep sections compact.
- Prefer examples when they clarify workflow boundaries.
- Avoid project-management filler.
- Do not add estimates, owners, priorities, or sprint assignments unless supplied.
- Use plain hyphens for authored title separators and avoid em dashes or vertical-bar prose separators.
