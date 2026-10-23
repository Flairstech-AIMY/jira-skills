# Review, reconciliation and Jira publication

Use this reference when a breakdown needs review, must be reconciled with existing Jira work, or will be published. Keep the process proportional to the number of issues and the user's authorization.

## Keep requirements traceable

For a multi-issue review, maintain a stable mapping from each source need to its Epic, feature, research decision or supporting Task. Keep confirmed decisions, illustrative examples, pending user questions and your recommendations distinguishable.

Apply a correction everywhere it affects the plan: narrative, completion conditions, examples, relationships and review flags. Preserve the user's terminology when it carries intent. Do not re-ask an answered question, or promote a proposed flow or review recommendation into a confirmed requirement.

## Reconcile existing work

Search the relevant project, then read the plausible matches. Compare actor, trigger, expected outcome, delivery scope and current evidence. Classify each candidate:

- **Duplicate:** the same feature or decision already has an authoritative issue.
- **Partial overlap:** some requirements are covered; identify the retained home and the distinct gap.
- **Prior work:** research or design that the new delivery can build on.
- **Related:** useful context with a different outcome, trigger or workflow.
- **Unrelated:** remove it from the proposed relationship.

A similar title or a Done/UAT status does not prove equivalent delivered functionality. Read what the issue actually delivers. A prototype-design Task can be complete while implementation remains outstanding. Preserve that distinction in the recommendation.

When the user identifies an existing issue as authoritative, reuse it rather than creating a duplicate. When they reject a match, remove that association and do not reintroduce it from a stale search result. Preserve their explicit instructions about whether to update, reuse unchanged or create distinct work.

## Prepare a review artifact when needed

If the user asks to review before Jira changes, or approval is required for the proposed mutation, make the proposal concrete first. For an HTML review, provide a readable standalone page with the relevant context, complete issue drafts, relationships, source references, unresolved decisions and a summary of proposed creates versus updates or reuse.

Local codes such as E1, S2 and R3 can support navigation. Show the actual proposed Jira parent and distinguish an HTML overview from an Epic to create. Explain how phases, shared work and completion checks will appear in Jira. Do not rely on visual grouping that disappears on publication.

Keep review-only material visibly separate:

- Questions addressed to the reviewing user
- Assignment reminders and names awaiting account resolution
- Duplicate-screen notes, suggested alternatives and change history
- Local draft codes and aliases

The problem narrative, confirmed workflow context, examples, Definition of Done, and research questions, evidence and outputs are substantive issue content.

For bulk work, retain a simple mapping of draft code, proposed action, parent reference and final Jira key. Use the user's destination and existing artifact conventions. Keep generated content and its source consistent so an answered question cannot return on regeneration.

## Map to supported Jira structure

Check the project's configured issue types and relevant fields. Do not assume a Research type, a phase field, nested Epics, or Story-to-Task parenting exists. Use the supported type that preserves the issue's purpose.

Give each child issue one valid parent, and keep top-level issues without an invented parent where the configured hierarchy requires that. Shared work stays in one place and is linked from other delivery groups. Use a common label or another verified grouping field when useful for a cross-epic view. Validate link type names and direction; a related reference is not automatically a blocker.

If phases are separate Epics, give each its own outcome and completion check. An earlier phase should not wait for a later enhancement to close. If a phase needs a capability owned elsewhere, link the specific deliverable rather than making it depend on an entire broad initiative without evidence. Research can proceed in parallel where the questions permit it.

## Publish within the authorized scope

Reuse the user's current-session project, field and authorization decisions. A review hold remains in effect until the user authorizes the mutation; authorization already granted does not need a new confirmation merely because a skill is being applied. Optional fields the user has allowed to remain unset should remain unset.

For an authorized create or update:

- Resolve local parent and cross-reference codes to the real Jira keys. Choose creation order or staged finalization so the final description contains real issue links, not draft labels or placeholder URLs.
- Exclude review-only notes and assignment reminders from descriptions. Apply confirmed ownership through supported Jira fields using verified account IDs.
- Keep illustrative intervals, targets and workflows illustrative unless confirmed as fixed behavior. Do not carry product-specific decisions into another project's defaults.
- For existing issues, preserve the allowed update boundary. If the request is "add transcription and change nothing else," make only that addition, including a matching completion condition where requested; do not reformat the whole ticket or alter other fields.
- Prefer a lossless content format when the tool supports one for a narrow edit. Read back the issue and compare the intended changes, checking unrelated returned fields where relevant.
- Confirm the keys and links actually created or updated. Keep reused issues out of the new-issue count, and record partial outcomes before any retry so successful creates are not duplicated.

## Review completion

Check coverage, duplicate outcomes, valid parent mapping, resolvable links, remaining user questions and meaningful completion evidence. Verify the generated artifact when available and report any material preview limitation honestly. If the review finds no worthwhile delivery change, say so without inventing more Stories or Tasks.
