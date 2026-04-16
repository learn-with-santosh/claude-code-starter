# 🤖 Claude Code Starter Kit

> A personal + community toolkit of Claude Code skills, CLAUDE.md templates, and boilerplate projects for full-stack developers.

## 📦 What's Inside

| Folder | Purpose |
|---|---|
| `.claude/skills/` | Reusable Claude Code skills (slash commands) |
| `.claude/agents/` | Specialized subagents |
| `.claude/hooks/` | Lifecycle automation hooks |
| `boilerplate/angular19/` | Angular 19 project CLAUDE.md + conventions |
| `boilerplate/nodejs-api/` | Node.js/Express/TypeScript CLAUDE.md + conventions |
| `boilerplate/fullstack-angular-node/` | Full-stack CLAUDE.md combining both |

---

## 🚀 Quick Start

### Use a skill in your project
```bash
# Copy skills into your project
cp -r .claude/skills/ your-project/.claude/skills/

# Then in Claude Code:
/code-review
/git-commit
/debug
/seo-audit
```

### Use a boilerplate CLAUDE.md
```bash
# For Angular 19 project
cp boilerplate/angular19/CLAUDE.md your-angular-project/CLAUDE.md

# For Node.js API
cp boilerplate/nodejs-api/CLAUDE.md your-api-project/CLAUDE.md

# For Full-stack
cp boilerplate/fullstack-angular-node/CLAUDE.md your-fullstack-project/CLAUDE.md
```

---

## 🛠 Skills Reference

| Skill | Trigger phrases | What it does |
|---|---|---|
| `code-review` | "review", "check code", "PR review" | Checks bugs, security, performance, style |
| `git-commit` | "commit", "write commit message" | Generates conventional commit messages |
| `debug` | "debug", "error", "not working" | Diagnoses errors with root cause + fix |
| `seo-audit` | "seo", "audit", "ranking", "meta tags" | Full on-page + technical SEO audit |
| `new-feature` | "add feature", "build", "implement" | Plans and scaffolds features end-to-end |
| `refactor` | "refactor", "clean up", "improve code" | Systematic code improvement |
| `write-tests` | "write tests", "add tests", "test this" | Generates unit + integration tests |

---

## 📁 Boilerplate Stacks

### Angular 19
- Angular 19 with standalone components
- TypeScript strict mode conventions
- RxJS patterns, signal-based state
- Capacitor Android / Electron targets

### Node.js API
- Express + TypeScript + Sequelize
- MySQL database conventions
- REST API structure and error handling
- JWT auth patterns

### Full-stack (Angular 19 + Node.js)
- Combined conventions for both layers
- Shared types strategy
- Monorepo or separate repo guidance

---

## 🤝 Contributing

This repo is maintained by [@santoshshelar](https://github.com/santoshshelar).  
PRs welcome — especially new skills and stack-specific CLAUDE.md templates.

---

## 📄 License

MIT
