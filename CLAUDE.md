# Claude Code Starter Kit — Repo Memory

## Purpose
This repo contains reusable Claude Code skills and CLAUDE.md boilerplates
for Angular 19 + Node.js/Express/MySQL full-stack projects.

## Repo Structure
```
.claude/skills/     — Reusable skills (copy to any project)
.claude/agents/     — Specialized subagents
.claude/hooks/      — Hook examples and configs
boilerplate/        — Stack-specific CLAUDE.md templates
  angular19/
  nodejs-api/
  fullstack-angular-node/
```

## When editing this repo
- Skills must use exact filename `<name>.md` inside `.claude/skills/`
- SKILL frontmatter required: `name`, `description`, `allowed-tools`
- Keep each skill under 200 lines
- CLAUDE.md files in boilerplate/ should be self-contained
- Update README.md skills table when adding new skills

## Primary stack this repo supports
- Angular 19 (standalone, signals)
- Node.js + Express + TypeScript + Sequelize
- MySQL
- Capacitor Android, Electron
