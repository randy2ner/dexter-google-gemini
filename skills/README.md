# Skills

This directory provides reusable Skill scaffolding and holds Skill source intentionally promoted for use across multiple projects. Project-specific Skill development belongs in `projects/<project>/skills/`.

Copy and adapt `_template/` inside the owning project when a Skill is authorized. Give each Skill its own lowercase kebab-case directory. Do not copy a project-specific Skill back to this root collection unless it has been deliberately generalized and reviewed for reuse.

## Recommended layout

- `SKILL.md`: instructions and metadata consumed by the skill system.
- `references/`: optional supporting guidance or source material.
- `scripts/`: optional deterministic helpers.
- `assets/`: optional files used by the skill.
- `CHANGELOG.md`: recommended once versions are shared for testing.

Replace every bracketed placeholder before sharing. Keep package-specific requirements with the Skill. For project work, place importable test copies in `projects/<project>/skill-exchange/ready-for-test/`; use the root exchange only for intentionally shared artifacts.
