---
name: doctor
license: MIT
description: "Diagnoses software failures by gathering evidence, tracking symptoms and hypotheses, and generating structured treatment plans. Models failures as medical cases — iterates until confident, then outputs a schema-based fix recommendation. Use when debugging errors, crashes, failing tests, broken builds, or production incidents."
metadata:
  author: Jordan Godau
  version: 0.2.0
  references:
    - 00_ROUTER.md
    - 01_SUMMARY.md
    - 02_TRIGGERS.md
    - 03_ALWAYS.md
    - 04_NEVER.md
    - 05_PROCEDURE.md
    - 06_FAILURES.md
  keywords:
    - diagnose
    - debug
    - investigate
    - evidence
    - hypothesis
    - treatment
    - error
    - crash
    - bug
    - failing
---

# INSTRUCTIONS

## Quick Start

1. **Initialize**: `./skill.sh init --patient "system-name"` — creates `.doctor/session.yaml`
2. **Record symptoms**: `./skill.sh symptom "API returns 500" --category error --evidence "logs show timeout"`
3. **Gather evidence**: `./skill.sh grep "connection timeout" --save` — agent picks terms, script returns matches
4. **Form hypotheses**: `./skill.sh hypothesize "Pool exhaustion" --confidence 65 --falsifiable "Pool metrics show available connections"`
5. **Iterate** steps 3–4 until confidence reaches ~80%+
6. **Diagnose**: `./skill.sh diagnose "Connection pool exhaustion" --confidence 85 --cause "Pool size too small"`
7. **Treat**: `./skill.sh treat --option "Increase pool size:Set pool_size=50:low" --recommend "Increase pool size"`

## Scope

- Produces diagnosis and treatment plans — does **not** execute fixes
- Idempotent: run repeatedly until confident
- All artifacts stored in `.doctor/` (session, evidence, treatment)

## Detailed Reference

Refer to `metadata.references` for triggers, constraints, failure modes, and the full procedure.
