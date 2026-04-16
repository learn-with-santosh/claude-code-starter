# Contributing

Thanks for contributing to this Claude Code Starter Kit!

## Adding a New Skill

1. Create `.claude/skills/<skill-name>.md`
2. Required frontmatter:
```yaml
---
name: skill-name
description: What this skill does. Include trigger keywords users would say.
allowed-tools: Read, Write, Bash, Grep, Glob  # only what's needed
---
```
3. Keep it under 200 lines
4. Add it to the skills table in `README.md`

## Adding a Boilerplate

1. Create `boilerplate/<stack-name>/CLAUDE.md`
2. Must include: stack, structure, conventions, commands, do-not-touch
3. Add entry to `README.md`

## Skill Writing Tips

- **description** is the most important field — Claude uses it for auto-activation
- Include keywords users would naturally say ("review", "fix", "deploy")
- Show output format so Claude's responses are consistent
- Reference CLAUDE.md conventions where relevant

## PR Checklist
- [ ] Skill file named correctly (`skill-name.md`, kebab-case)
- [ ] Frontmatter complete (`name`, `description`, `allowed-tools`)
- [ ] README updated
- [ ] Tested locally in a real Claude Code session
