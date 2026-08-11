# skills

Public [Cursor](https://cursor.com) and [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skills for API developer experience work.

By [Aliza Solomon](https://www.linkedin.com/in/alizas/).

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

- Contradictions between published artifacts (prose vs spec, sample vs schema, deprecated paths still documented)
- Places where a first-time integrator has to guess on the happy path
- Obvious gaps when you cannot finish “This API lets a developer ___” from the in-scope surface alone

## What it does not cover

This is a **free, lightweight review**.

It is relatively strong on **contradictions**. It is weak on **absences**: undocumented semantics, missing read-back paths, error behavior that is never specified, async write semantics, cross-surface gaps. Those usually need a human review that traces the job across surfaces, or a paid review.

If you want the fuller picture of how I evaluate APIs, see [dx-evaluation-framework](https://github.com/alizas1/dx-evaluation-framework) (essays + methodology).

## Attribution

Free to use and adapt. If you share or fork, keep attribution and link back to this repo.

## Topics

`claude-skill` · `agent-skills` · `cursor` · `api` ·  `api-documentation` · `devrel` · `developer-experience`
