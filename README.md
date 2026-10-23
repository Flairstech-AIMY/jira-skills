# Jira Skills

Reusable Jira product ownership and MADS project-management skills for Claude Code, OpenAI Codex, and GitHub Copilot. The skills are written in the open `SKILL.md` format and kept under `skills/` so they can be installed selectively with the Skills CLI or copied into an agent's standard skills directory.

## Available skills

- [`jira-product-owner`](skills/jira-product-owner/SKILL.md) - General product ownership and Jira planning.
- [`jira-feature-breakdown`](skills/jira-feature-breakdown/SKILL.md) - Notes to Epics, user features, focused research and minimal technical Tasks; phased delivery and deliverability review.
- [`jira-research-task`](skills/jira-research-task/SKILL.md) - Investigations with problem context, decision boundaries, questions, evidence, expected outputs and verifiable completion.
- [`jira-database-deployment`](skills/jira-database-deployment/SKILL.md) - Focused database-deployment and migration-pipeline tickets.
- [`jira-ai-behavior-story`](skills/jira-ai-behavior-story/SKILL.md) - Testable conversational AI and voice-agent behavior Stories.
- [`jira-production-incident`](skills/jira-production-incident/SKILL.md) - Production incidents and operational failures.
- [`jira-ticket-refiner`](skills/jira-ticket-refiner/SKILL.md) - Refining a ticket while preserving intent, evidence and the authorized edit boundary.
- [`jira-user-outcome-story-refiner`](skills/jira-user-outcome-story-refiner/SKILL.md) - User features and observable outcomes instead of engineering activities disguised as Stories.
- [`jira-implementation-neutral-task-breakdown`](skills/jira-implementation-neutral-task-breakdown/SKILL.md) - Minimal supporting engineering work while leaving design choices to the team.
- [`jira-ticket-writer`](skills/jira-ticket-writer/SKILL.md) - Jira-ready issues from rough input with enough context to understand the problem.
- [`jira-description-format`](skills/jira-description-format/SKILL.md) - Narrative-first issue content, plain separators and clean separation from review notes.
- [`mads-project-management`](skills/mads-project-management/SKILL.md) - MADS tools and links between MADS work and Jira planning.

## Team workflow

Start a broad planning request with `jira-product-owner` or `jira-feature-breakdown`. Use the focused skills for the specific issue or research decision rather than loading every skill for every request.

- Understand the need before assigning issue types: needs, then Epics, then user-facing Stories, supporting research and only the technical Tasks useful to plan now.
- Preserve workflow context and confirmed examples so engineers understand the problem and can choose a solution. Engineers can create implementation Tasks and suggest more Stories after research.
- Ask for missing product intent; investigate a method when the user has delegated that choice. Keep research questions and decision outputs concrete.
- Reconcile existing Jira work by its actual scope. Distinguish a duplicate feature from prior design, completed research, related work and an unrelated match.
- Represent phases using supported Jira hierarchy and fields. Shared work has one home, with links from the features that use it.
- When a review artifact is needed, keep local codes, assignment reminders and reviewer questions separate from publishable issue content. Resolve references to real Jira links and verify the authorized mutations.
- Treat user corrections as updates to the affected drafts. Remove answered flags and keep review suggestions distinguishable from approved scope.
- Default authored titles and prose to plain hyphen separators. Preserve exact source material or a requested format when needed.

Project keys, platforms, intervals, targets and setting precedence belong to the individual engagement. Do not turn one project's confirmed rules into defaults for the whole team. The [review examples](skills/jira-feature-breakdown/references/review-examples.md) illustrate how to handle these decisions without hardcoding them.

## Install

Install the skills interactively for the agents available in your environment:

```sh
npx skills add Flairstech-AIMY/jira-skills
```

Install all skills explicitly for Claude Code, Codex, and GitHub Copilot:

```sh
npx skills add Flairstech-AIMY/jira-skills \
  --skill jira-product-owner \
  --skill jira-database-deployment \
  --skill jira-ai-behavior-story \
  --skill jira-feature-breakdown \
  --skill jira-research-task \
  --skill jira-production-incident \
  --skill jira-ticket-refiner \
  --skill jira-user-outcome-story-refiner \
  --skill jira-implementation-neutral-task-breakdown \
  --skill jira-ticket-writer \
  --skill jira-description-format \
  --skill mads-project-management \
  --agent claude-code \
  --agent codex \
  --agent github-copilot
```

Add `--global` to install for your user rather than the current project. To install only one skill, omit the other `--skill` option. Use the CLI's `--list` option to inspect available skills before installing.

Skills CLI: <https://skills.sh/>  
GitHub Copilot skills: <https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills>  
Claude Code skills: <https://code.claude.com/docs/en/skills>  
Codex skills: <https://developers.openai.com/codex/skills/>

## Manual installation

Copy a skill's whole folder (including its `SKILL.md`) into the appropriate project directory:

- Claude Code: `.claude/skills/`
- Codex: `.agents/skills/`
- GitHub Copilot: `.github/skills/`

For user-level installation, use the agent's documented personal skills directory. Restart or refresh the agent if it does not discover a newly installed skill.

After repository updates are shared, refresh the team's installed skills using the normal installation process or copy the updated whole folders. Existing copied installations do not automatically receive changes from this repository; include referenced resources as well as `SKILL.md`.

## Design principles

- Keep the skills portable across products and teams; do not assume a particular Jira project, workflow, cloud provider, or tool integration.
- Preserve the user's intent, do not invent missing facts, and ask for material details before creating Jira issues.
- Keep issue content focused on user value and outcomes. Avoid unnecessary implementation detail and never put secrets or credentials in tickets.
- Keep the Jira Summary separate from the Description: do not repeat the title as a heading or first line in the Description.
- Use Jira integration tools only when available, and be explicit about what has and has not been created.
