# skills

Public [Cursor](https://cursor.com) and [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skills for API developer experience work.

By [Aliza Solomon](https://www.linkedin.com/in/alizas/), alizasolomondx@gmail.com.

## Skills

| Skill | What it does |
|-------|----------------|
| [`api-friction-pass`](api-friction-pass/SKILL.md) | Reads integrator-facing docs/spec, picks 1–2 real use cases, checks the docs/spec against the use cases, and lists where someone would get stuck finishing them |

More skills may land here over time. Each skill lives in its own folder with a `SKILL.md`.

## Quick start

1. Copy the skill folder you want into your agent skills directory (see install below).
2. In Cursor or Claude, ask for an **API friction pass** and point at your docs URL, files, or spec.
3. The skill locks scope, states what the API lets a developer do, picks use cases, walks the path, and lists findings in chat.

**Example ask:** “Run an API friction pass on https://developers.example.com.”

## Install

### Cursor

Copy `api-friction-pass/` to one of:

- **Project:** `.cursor/skills/api-friction-pass/`
- **User (all projects):** `~/.cursor/skills/api-friction-pass/`

Restart Cursor or start a new chat if the skill does not show up.

### Claude Code

Copy `api-friction-pass/` to one of:

- **Project:** `.claude/skills/api-friction-pass/`
- **User:** `~/.claude/skills/api-friction-pass/`

Or clone this repo and symlink the folder into your skills path.

## What `api-friction-pass` is good for

This is a free, lightweight review of up to 2 use cases as chosen by the agent (unless you provide your own). Different passes can surface different findings if the use cases or scope change.

It is relatively strong on **contradictions**:
- Contradictions between published artifacts (prose vs spec, sample vs schema, deprecated paths still documented)
- Places where a first-time integrator has to guess the happy path
- Obvious gaps

It is weaker on **absences**: undocumented steps or semantics, error behavior that is never specified, cross-surface gaps. It is also weak on finding the most important jobs to check. Those usually need a human review that traces the job across multiple surfaces.

This is not a deterministic OpenAPI check against a fixed signal set, or an AI-readiness assessment of the contract. It intentionally focuses on one specific facet of developer experience: the walkthrough.

If you want the fuller picture of how I evaluate APIs, see [dx-evaluation-framework](https://github.com/alizas1/dx-evaluation-framework) (essays + methodology).

## Attribution

Free to use and adapt. If you share or fork, keep attribution and link back to this repo.
