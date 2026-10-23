---
name: jira-description-format
description: Format Jira issue descriptions without repeating the issue title in the description body. Use when drafting, creating, or editing a Jira description, especially when converting a Jira ticket template into content for the Description field.
---

# Jira Description Format

Keep the Jira issue Summary and Description distinct. Jira already displays the Summary as the issue title, so do not repeat the Summary in the Description.

## Rules

- Never start a Jira Description with an H1 that repeats the issue Summary or title.
- Begin the Description with a short plain-prose narrative: the need, the idea behind the user's expectation, and the story behind the request. Do not open with a header, and never with `## Business Context`.
- Include enough current workflow, concrete difficulty and confirmed examples for an engineer to understand the problem without reading the planning chat. Concise does not mean removing useful context.
- Headers may appear only after that opening narrative, and only when they add structure (for example, `## Definition of Done`).
- Do not include `## Suggested Owner`, `## Estimate`, `## Dependencies`, or `## Technical Notes` sections unless the user explicitly asks for that information. Never add them as defaults or placeholders (including "TBC").
- Do not repeat the title as an unformatted first line either.
- Preserve a title in a standalone ticket document only when the output is intended to be a document rather than Jira Description field content.
- When editing an existing issue, remove a duplicated title heading from the Description without changing the Summary or the ticket's intent.
- Before creating or updating a Jira issue, verify that its Description does not repeat the Summary.
- Default authored titles and prose to plain hyphen separators. Avoid em dashes and vertical-bar separators unless preserving exact source material or a specifically requested format.
- Keep drafting commentary such as "the note asks for this but supplies no baseline" outside issue content. Describe the actual observed problem; ask the user for missing intent or put the investigation in a research item.
- During review, keep local codes, assignment reminders and questions for the user separate from the publishable description. Replace draft references with verified Jira links on publication. Research scope, evidence, questions and expected outputs are substantive issue content, not review notes.
- A narrowly authorized edit takes precedence over cleanup rules. If asked to change only one point, preserve the rest of the existing description and fields, including legacy formatting.

## Example

Summary:

`Document Workspace - Uploads - Upload Multiple Files`

Description:

```markdown
Users currently have to upload files one at a time, which slows down workflows where they
need to share several documents together. They expect to select everything once and
have it handled as a single action...

## Definition of Done
- Users can select and upload multiple files in one action.
```

Do not put `# Document Workspace - Uploads - Upload Multiple Files` at the top of the Description.
