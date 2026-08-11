---
name: api-friction-pass
description: >-
  Walk an API's integrator-facing docs and spec like a first-time integrator.
  Surface where someone would get confused or fail to finish a real use case. Use
  when checking public docs or draft docs before publishing.
---

# API friction pass

Read **only the integrator-facing surface in scope** that the user defines. No internal knowledge, repo, or team chat unless it is inside the user-defined surface. Find where a first-time integrator would get confused, guess wrong, or fail to finish a real use case, and list them.

## How to use this skill

Ask for an API friction pass and provide the published docs URL, files, or spec you want reviewed.
This workflow will check the API's purpose, define use cases, check the docs against these use cases, and provide a list of places where an integrator is likely to get stuck.

## Workflow

### 1. Lock scope
Ask only if missing: which docs URL, files, or spec are in scope?
Do not invent that surface. 
Note whether the surface looks published or draft when that's obvious from what you can open. If you can't tell and it would change the pass, ask.
If the in-scope surface is still unclear, ask before reading deeply.

### 2. API purpose 
Complete in one sentence: **"This API lets a developer ___."** Print this in the chat.
Write it from the outside — what someone can accomplish, not how the system works inside.
If you cannot finish that sentence confidently from the in-scope surface alone, that gap is itself a finding.

### 3. Pick 1–2 real use cases
Write 1–2 concrete scenarios a real integrator would attempt (not "use the API") and print them in the chat.
Example shape: "Create X, then update Y, then confirm Z from the response."
These use cases anchor the rest of the pass. When unsure whether something matters, ask: *would someone pursuing one of these use cases actually hit this?*

### 4. Follow the path like an integrator
Using only the in-scope surface, follow the path for those use cases. Prefer noticing anomalies ("that doesn't fit").
Use these prompts (skip any that don't apply):
- Do names and descriptions match what the call actually does?
- If I follow the happy path, where do I have to guess?
- Are examples copy-pasteable, and do they match the contract?
- When something fails, do errors tell me what to do next?
- if an agent only has the OpenAPI / schema / examples in the contract, is the important shape still there?
Stay with contradictions. If two surfaces in scope disagree, say so. If you need an answer that only exists outside the user-defined surface, that is a finding — do not fill it from insider knowledge.

### 5. Write findings
For each real issue, write in the chat:
- **What broke** — the concrete confusion or failure
- **Where** — page, endpoint, field, example, or spec path
- **Why it matters** — which use case from step 3 it blocks or slows.
Drop nitpicks that would not affect those use cases.
End with the purpose sentence (or the gap if missing), the 1–2 use cases, and the findings.
