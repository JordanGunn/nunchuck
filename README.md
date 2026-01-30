# Nunchuck

> **Deprecation Notice**
> This repository is being deprecated in favour of more focused skill repositories. The creation of this repository is what led to the first draft of the ASI (Agent Skills Interface) governance specification, the OASR (Open Agent Registry) CLI, and the AUx tools. While these skills were strong in spirit, **all of them will be reworked, improved and moved to dedicated repositories.**
> I will leave this repository in the meantime since people seem to he using. I will update this notice with the new and improved skill repos as i develop them. Cheers! 

A rigorously structured collection of agent skills designed to reduce drift, enforce determinism, and make agentic work auditable. Built on the [Open Agent-Skill Specification](https://github.com/JordanGunn/agent-skill-spec) and extended with internal specifications that define canonical structures, execution patterns, and epistemic guardrails.

---

## Documentation

- **[Quickstart Guide](./docs/QUICKSTART.md)** — Getting started
- **[Skills Reference](./docs/SKILLS.md)** — Browse all available skills
- **[Contributing](./CONTRIBUTING.md)** — Add your own skills

---

## Design Philosophy

This repository treats language as inherently ambiguous and builds systems that succeed *despite* that ambiguity. Three principles guide all skill design:

- **Determinism First, Subjectivity Last** — Subjective reasoning must never compensate for missing deterministic outputs. If evidence is incomplete, return to earlier execution phases rather than explaining around gaps.

- **Artifacts as Completion Signals** — Success is mechanically verifiable. Skills declare what they produce; validation checks existence. Missing artifacts redirect execution to producing steps.

- **Professional Skepticism** — Agents interpret, clarify, and challenge rather than blindly comply. User input is valuable but not authoritative truth. Responsibility for correctness cannot be outsourced.

These principles are formalized in the [Design Documentation](./docs/design/.INDEX.md), which includes epistemic tenets, interaction tenets, and a determinism framework.

---

## Specification Compliance

### Open Agent-Skill Spec

All skills conform to the [Open Agent-Skill Specification](https://github.com/JordanGunn/agent-skill-spec), ensuring portability across agent platforms. Each `SKILL.md` contains frontmatter-only definitions with explicit metadata for references, scripts, and keywords.

### Internal Specifications

Beyond the open spec, this repository enforces internal specifications that define:

- **[SKILL.md Structure](./docs/design/specs/skillmd/.INDEX.md)** — Frontmatter schema, body constraints, validation rules
- **[References Structure](./docs/design/specs/references/.INDEX.md)** — Canonical 7-file reference set (`00_ROUTER` through `06_FAILURES`)
- **[Scripts Structure](./docs/design/specs/scripts/.INDEX.md)** — Cross-platform script requirements and naming

These specifications ensure consistency across all skills and enable tooling to validate compliance.

---

## Skills

All skills live in the `skills/` directory. Browse them directly or use the reference documentation:

- **[Skills Reference](./docs/SKILLS.md)** — Complete list of skills with descriptions and keywords

---

## Usage

See the **[Quickstart Guide](./docs/QUICKSTART.md)** for installation, IDE integration, and first steps.

---

## Scripts

Utility scripts provide thin integration layers without duplicating skill content. Skills remain spec-compliant so they transfer cleanly when IDEs adopt agent skills natively.

### IDE Adapters

Generate IDE-specific configurations that reference skills without copying them:

```bash
# Windsurf: generates .windsurf/workflows/
bash scripts/adapters/windsurf/run.sh --skills-root skills --output-root .

# Cursor: generates .cursor/commands/
bash scripts/adapters/cursor/run.sh --skills-root skills --output-root .
```

Windows (PowerShell):

```powershell
.\scripts\adapters\windsurf\run.ps1 --skills-root skills --output-root .
.\scripts\adapters\cursor\run.ps1 --skills-root skills --output-root .
```

### Index Generator

---

## Changelog

See [CHANGELOG.md](./CHANGELOG.md) for release history.

## License

See [LICENSE](./LICENSE) for details.
