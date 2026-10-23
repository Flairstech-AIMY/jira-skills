---
name: jira-research-task
description: Draft or refine Jira research items that return an evidence-backed decision for a product need. Use when a feature needs product discovery, technical feasibility analysis, UI/UX research, or a comparison before delivery can be scoped. Keep the research distinct from the user feature and from implementation tasks.
---

# Jira Research Task

Give the investigator enough problem context to choose and evaluate a solution. The deliverable is a supported decision or recommendation, with findings that can refine the backlog.

## Establish the decision

- Start with who needs help, the current workflow or difficulty, and the outcome the research supports. Explain why the decision matters before listing investigation activities.
- Preserve confirmed scope, terminology, examples, constraints and prior work. A platform can be confirmed while its joining method remains a research question.
- Separate missing product intent from an unresolved solution. Ask the user for a business decision they have not delegated; investigate a method they have explicitly delegated rather than asking them to design it.
- Give each research item a distinct decision and boundary. Separate product, technical and UI/UX investigations when they need different evidence or useful independent outputs. Do not split mechanically by discipline or create duplicate investigations.
- Link to the feature and related research. Say what this investigation owns and what another item owns when their scopes meet.

## Define useful research

Choose the sections that help the investigator answer the decision:

- **Research scope:** the decision, initial scenarios and exclusions supported by the request.
- **Questions to answer:** focused questions whose answers can change the recommendation or delivery boundary.
- **Evidence to examine:** relevant current workflows, records, prior designs, official capabilities, representative examples, measurements or a focused feasibility check. Distinguish evidence already inspected from work still to do.
- **Expected outputs:** a recommendation with tradeoffs, a decision flow, comparison, reviewable examples, prototype findings, or a scenario-to-source map as appropriate.
- **Definition of Done:** observable evidence that the question has been answered, the recommendation is justified, and remaining unknowns are explicit.

Keep the investigation bounded by a decision and representative scenarios. Do not invent a duration, estimate, owner or performance threshold. A documented finding that an option is infeasible can complete research.

## Engineering freedom

- Preserve a required technology or named candidate, but do not assume the candidate achieves the goal. Investigate its suitability and limitations.
- Tie feasibility, latency or cost findings to the actual user journey and relevant baseline. Recommend measurable delivery criteria from the findings instead of inventing targets.
- Make the team aware of the problem and constraints without prescribing an architecture, vendor or sequence of code changes that has not been selected.
- Ask for the minimum delivery work and additional Stories revealed by the findings. Do not automatically turn every possible approach into a technical Task.
- Feed the selected scenarios and decisions back into the supported Stories before sprint commitment. Research completion alone does not mean the feature has been delivered.

## Description shape

Keep the title in Jira Summary. Open Description with a short narrative, then use only the sections needed:

```markdown
[Who needs the outcome, what happens today, and why this decision is needed.]

## Research scope
[Decision and boundary, including relevant related work.]

## Questions to answer
- [A question that affects the recommendation]

## Evidence to examine
- [Evidence or feasible method of investigation]

## Expected outputs
- [A reviewable decision or artifact]

## Definition of Done
- [How the recommendation and its supporting evidence can be checked]
```

These research sections are real issue content. Assignment reminders, drafting commentary and questions addressed to the reviewing user belong outside the publishable description. Use plain hyphen separators in titles; replace local review codes with verified Jira links when publishing.

Before creating the item, verify the project's supported issue types. Use its Research or Spike type when available, or a Task with an explicit investigation objective when appropriate; do not assume a type or field exists.
