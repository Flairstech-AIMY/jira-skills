# Jira Skills

Reusable Jira product ownership skills for Claude Code, OpenAI Codex, and GitHub Copilot. The skills are written in the open `SKILL.md` format and kept under `skills/` so they can be installed selectively with the Skills CLI or copied into an agent's standard skills directory.

## Available skills

| Skill | Use it for |
| --- | --- |
| [`jira-product-owner`](skills/jira-product-owner/SKILL.md) | Turning requirements into clear Jira stories, tasks, bugs, research items, epics, and initiative breakdowns. |
| [`jira-database-deployment`](skills/jira-database-deployment/SKILL.md) | Creating focused database-deployment and migration-pipeline tickets. |
| [`jira-ai-behavior-story`](skills/jira-ai-behavior-story/SKILL.md) | Writing testable conversational AI and voice-agent behavior Stories. |
| [`jira-feature-breakdown`](skills/jira-feature-breakdown/SKILL.md) | Breaking initiatives into outcome-based Stories and supporting Tasks. |
| [`jira-production-incident`](skills/jira-production-incident/SKILL.md) | Turning production incidents and operational failures into focused Jira issues. |
| [`jira-ticket-refiner`](skills/jira-ticket-refiner/SKILL.md) | Refining an existing Jira ticket while preserving intent and supported requirements. |
| [`jira-ticket-writer`](skills/jira-ticket-writer/SKILL.md) | Drafting concise Jira Stories, Tasks, Bugs, or investigation items from rough input. |

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
  --skill jira-production-incident \
  --skill jira-ticket-refiner \
  --skill jira-ticket-writer \
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

For user-level installation, use the agent's documented personal skills directory. Restart or refresh the agent if it does not discover a newly added skill.

## Design principles

- Keep the skills portable across products and teams; do not assume a particular Jira project, workflow, cloud provider, or tool integration.
- Preserve the user's intent, do not invent missing facts, and ask for material details before creating Jira issues.
- Keep issue content focused on user value and outcomes. Avoid unnecessary implementation detail and never put secrets or credentials in tickets.
- Use Jira integration tools only when available, and be explicit about what has and has not been created.
