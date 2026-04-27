---
name: sniff-bloaters
license: MIT
description: "Detects bloater code smells (Long Method, Large Class, Long Parameter List) using deterministic heuristics and appends findings to .sniff/findings.jsonl. Scans tracked files via git ls-files and regenerates index. Use when checking code quality, looking for code smells, reviewing method length, class size, or parameter list issues."
metadata:
  author: Jordan Godau
  version: 0.1.0
  references:
    - 00_ROUTER.md
    - 01_SUMMARY.md
    - 02_TRIGGERS.md
    - 03_ALWAYS.md
    - 04_NEVER.md
    - 05_PROCEDURE.md
    - 06_FAILURES.md
  scripts:
    - scripts/skill.sh
    - scripts/skill.ps1
  keywords:
    - sniff
    - bloaters
    - smell
    - long-method
    - large-class
    - long-parameter-list
    - code-quality
    - refactor
---

# INSTRUCTIONS

## Quick Start

1. **Validate**: `scripts/skill.sh validate` — checks prerequisites and environment
2. **Scan**: `scripts/skill.sh scan` — scans tracked files for bloater smells

## Outputs

- `.sniff/findings.jsonl` — append-only findings ledger
- `.sniff/index.json` — regenerated summary index
- `.sniff/state.json` — regenerated scan state

## Scope

- Scans files deterministically via `git ls-files`
- Detects Long Method, Large Class, and Long Parameter List smells
- Does **not** refactor or fix — detection only
- Findings are never deleted from the ledger

## Detailed Reference

Refer to `metadata.references` for triggers, constraints, failure modes, and the full procedure.
