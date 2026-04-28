---
name: plan-create
license: MIT
description: "Compiles a plan intent artifact (.plan/active.yaml) into a schema-validated active plan directory at .plan/active/. Generates objective, success criteria, sub-plan structure, and task work steps. Use when building a plan, generating a project plan, compiling active.yaml, or scaffolding plan structure."
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
  assets:
    - assets/plan-root-schema.json
    - assets/plan-subplan-schema.json
    - assets/plan-task-schema.json
    - assets/plan-discuss-artifact-schema.json
  keywords:
    - plan
    - create
    - scaffold
    - initialize
    - compile
    - build
    - generate
---

# INSTRUCTIONS

## Quick Start

1. **Ensure intent is ready**: Use `plan-discuss` until `.plan/active.yaml` has `status: ready`
2. **Compile**: Run `scripts/skill.sh` — creates/overwrites `.plan/active/` from `.plan/active.yaml`
3. **Validate**: Compilation produces schema-valid plan files; if it fails, fix `.plan/active.yaml` and re-run

## Scope

- Defines objective, success criteria, sub-plan structure, and task work steps
- Frontmatter for `plan.md`, `index.md`, and task files is schema-validated
- Does **not** execute the plan — that is `plan-exec`

## Detailed Reference

Refer to `metadata.references` for triggers, constraints, failure modes, and the full procedure.
