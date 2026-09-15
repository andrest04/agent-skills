# agent-skills

[![skills.sh](https://skills.sh/b/andrest04/agent-skills)](https://skills.sh/andrest04/agent-skills)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Reusable [Agent Skills](https://agentskills.io) for coding agents — Claude Code, Cursor, Codex, and 75+ others supported by the [`skills` CLI](https://github.com/vercel-labs/skills). Each skill teaches an agent a specific piece of procedural knowledge instead of relying on it to remember or reinvent it every time.

## Install

```bash
# All skills
npx skills add andrest04/agent-skills

# One specific skill
npx skills add andrest04/agent-skills --skill design-patterns
```

## Skills

| Skill | Description |
| --- | --- |
| [`design-patterns`](skills/design-patterns/SKILL.md) | Choose and apply the right software design pattern or architecture style: GoF catalog (aligned to [refactoring.guru](https://refactoring.guru/design-patterns/catalog)), SOLID as forces not a checklist, Clean/Hexagonal/Screaming Architecture, Atomic Design, Container/Presentational. |

More skills land here over time — this is a living collection, not a one-off drop.

## Adding or updating a skill

1. Create `skills/<name>/SKILL.md` (frontmatter: `name`, `description`, `license`, `metadata.author`, `metadata.version`) plus a `rules/<category>-<slug>.md` file per concept it covers — see `skills/design-patterns` for the reference layout.
2. Update the table above.
3. Commit and push to `main` — skills.sh reads straight from the repo, there's no separate publish step.

## License

MIT — see [LICENSE](LICENSE).
