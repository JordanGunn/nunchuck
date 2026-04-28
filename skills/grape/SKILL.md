---
name: grape
license: MIT
description: "Searches codebases using grep to find functions, classes, strings, or patterns across files. Converts vague intent into explicit, auditable grep parameters and executes a portable disk scan. Use when you need to locate files, find where a term appears, search code, or perform breadth-first codebase discovery before reading."
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
    - scripts/skill.sh
    - scripts/skill.ps1
  keywords:
    - grep
    - search
    - discovery
    - surface
    - ripgrep
    - find
    - locate
    - codebase
---

# INSTRUCTIONS

## Quick Start

1. Gather the user's search intent — what concept or term to find
2. Choose parameters — root directory, patterns, include/exclude globs, match mode
3. Run the search via CLI:
   ```bash
   ./scripts/skill.sh grep --root . --pattern "term" --mode fixed --case smart
   ```
4. Interpret results — use file paths and distributions to refine or select next steps

## Scope

- Answers **where** things live, which files are involved, and whether a term appears
- Does not explain behavior, architecture, or semantics
- Output is deterministic and reproducible for a given parameter set

## Detailed Reference

Refer to `metadata.references` for contracts, triggers, failure modes, and the full procedure.
