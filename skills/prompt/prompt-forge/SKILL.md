---
name: prompt-forge
license: MIT
description: "Drafts, iterates, and finalizes prompts for LLMs. Collaboratively shapes user intent into a structured prompt artifact at .prompt/active.yaml, clarifying ambiguity until the user confirms readiness. Use when writing a prompt, doing prompt engineering, refining instructions, or crafting a system prompt."
metadata:
  author: Jordan Godau
  version: 0.1.0
  references:
    - 00_ROUTER.md
    - 01_SUMMARY.md
    - 02_CONTRACTS.md
    - 03_TRIGGERS.md
    - 04_NEVER.md
    - 05_ALWAYS.md
    - 06_PROCEDURE.md
    - 07_FAILURES.md
  scripts:
    - forge.sh
    - forge.ps1
    - validate.sh
    - help.sh
  assets:
    - assets/prompt-artifact-schema.md
    - assets/prompt-artifact-schema.json
    - assets/receipt-schema.json
    - assets/observability-template.md
  artifacts:
    - .prompt/active.yaml
  keywords:
    - prompt
    - forge
    - refine
    - clarify
    - intent
    - draft
    - write
    - engineer
    - instructions
---

# INSTRUCTIONS

## Quick Start

1. **Check state**: Run `./scripts/forge.sh` — creates `.prompt/active.yaml` if it does not exist, shows current status
2. **Propose updates**: From conversation, propose changes to intent fields (objective, constraints, assumptions, open questions) and prompt text
3. **Persist changes**: Edit `.prompt/active.yaml` with confirmed updates, then re-run `./scripts/forge.sh` to validate
4. **Mark ready**: When user explicitly confirms, run `./scripts/forge.sh --mark-ready`
5. **Handoff**: Stop after artifact is stable — subsequent actions happen in other skills

## Scope

- Maintains a single prompt artifact at `.prompt/active.yaml`
- Acts as a collaborative editor — clarifies intent, persists to disk, does not execute prompts
- All state changes are explicit and auditable

## Detailed Reference

Refer to `metadata.references` for contracts, triggers, failure modes, and the full procedure.
Use scripts: `forge.sh` (state/validation), `validate.sh` (schema check), `help.sh` (usage info).
