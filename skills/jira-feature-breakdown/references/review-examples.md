# Examples from collaborative backlog review

Use these examples to check decisions in ambiguous notes or revisions. They are portable illustrations, not default scope, project settings or mandatory ticket counts. A later explicit user instruction overrides an example.

## A technical idea needs its business reason

Input: "Switch the transfer mechanism." The user clarifies that billing continues throughout the human-to-human conversation after handoff.

Expected treatment: retain the cost problem as the need. Research whether the proposed mechanism actually reduces the ongoing charges, then make delivery conditional on that finding. Do not assume a named transport or vendor eliminates the cost, or turn the mechanism switch into a new user Story merely by changing its wording.

## An uncertain interface can still support a clear Story

Input: a sales user cannot call a new person because the flow requires an existing contact. They consider adding a contact first, a dial button, or offering to save the contact afterward, but do not choose a flow.

Expected treatment: draft the feature as calling a person who is not yet saved while keeping useful contact history. Preserve the dead end and the considered flows as context. Use product/technical and UI/UX research where distinct decisions require them. Do not mandate the dial button or replace the user feature with research alone.

## Different wording may describe one feature

Input: one draft says "get better help from earlier investigations" and another says "benefit from reviewed corrections in later interactions."

Expected treatment: compare the actual actor, trigger and outcome. Merge if both promise the same later-interaction improvement, while preserving both confirmed expectations and their examples. Let research identify any genuinely separate user feature. Do not split simply by retrieval, storage or behavior-change mechanisms.

## Confirmed scope and delegated method are different

Input: the user selects Microsoft Teams for meetings and says how the assistant joins needs its own research. They also restrict the first collaboration tasks to read-only work.

Expected treatment: keep Teams and read-only work as constraints for this engagement. Create focused joining research and a joining feature with the method still open. Do not ask the user to choose the joining mechanism again. Do not generalize Teams or read-only scope to future unrelated requests.

## Keep examples and configuration rules distinct

Input: retry intervals are campaign-configurable examples. Separately, the user explicitly confirms that campaign email settings override product settings, which override client settings.

Expected treatment: retain the retry example without making its intervals universal. Apply the confirmed sending precedence to that feature, including both enabled and disabled choices, and remove its answered review flag. Do not infer that the same hierarchy governs other settings or invent a default when no scope has a value.

Similarly, a user may confirm adding unfinished calls to the next day's normal target while saying that 500 calls is only an example. Preserve the carryover rule and the illustrative calculation, without turning 500 into a fixed target or introducing that carryover policy into unrelated goal features.

## Preserve vocabulary and observed facts

Input: the user asks for the term "hierarchy" and reports that telephone replies are roughly one to three seconds slower than a direct browser voice path.

Expected treatment: use hierarchy consistently in the affected feature. Preserve the reported comparison as context for performance research. Ask for missing intent if needed; do not put "the notes supplied no baseline" into the Story or invent a numerical improvement target.

## A review page must survive the move to Jira

Input: an HTML page shows five delivery phases under one visual overview, and the user asks how that structure appears in Jira.

Expected treatment: inspect the available hierarchy and propose explicit parent mapping. Separate substantial phases into Epics when useful, or use an appropriate supported grouping for smaller phases. Keep shared work in one home and link it. Do not assume the exact number of Epics from this example is a team-wide rule, or create an extra umbrella Epic solely because the HTML has an overview heading.

## Review codes and narrow updates

Input: the page uses R1 and S2 as navigation labels, names suggested assignees, and the user requests only adding transcription to a particular existing issue.

Expected treatment: review codes and assignment reminders stay in the review layer. Published relationships use verified Jira links and actual fields. Make and verify only the authorized transcription addition; preserve the rest of the issue. Do not create a duplicate or perform unrelated title and formatting cleanup.

## A review may require no changes

Input: "Review deliverability; it is fine if nothing needs changing."

Expected treatment: return only supported improvements, with the affected issues and the delivery reason. It is acceptable to find none. Keep suggestions distinguishable from user-approved scope and do not edit the breakdown when the request is critique only.
