# Skills — OpenCode

Reusable procedural instructions (skills/runbooks) relevant to this OpenCode
workspace. A skill is a directory with a `SKILL.md` file and a clear
`description` in frontmatter:

```text
skills/<skill-id>/
├── SKILL.md
├── scripts/
└── references/
```

## OpenCode V2 discovery

Official docs: https://opencode.ai/docs/skills/

- Built-in skills are available by default.
- Native paths: `~/.config/opencode/skills` (global), `.opencode/skills`
  (project).
- Compatibility paths: `~/.claude/skills`, `.claude/skills`, `~/.agents/skills`,
  `.agents/skills` — Claude Code-style `SKILL.md` skills are discovered.
- Extra local directories or HTTP catalogs can be added via the `skills` array
  in `opencode.jsonc`.

Notes:
- The skill ID comes from the file path, not the frontmatter `name`.
- A `.opencode/skills` skill overrides a same-ID skill from `.claude/skills`.
- This folder is the workspace record; to make a skill active here, place it
  under `.opencode/skills/` in this workspace or add `"./skills"` to `skills`
  in an applicable `opencode.jsonc`.
