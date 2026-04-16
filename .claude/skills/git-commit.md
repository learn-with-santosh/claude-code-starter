---
name: git-commit
description: Generate a conventional commit message from staged changes. Triggers on "commit", "write commit message", "git commit", "what should I commit".
allowed-tools: Bash
---

# Git Commit Skill

## Steps
1. Run `git diff --staged` to see all staged changes
2. Identify the commit type from changes:
   - `feat` — new feature
   - `fix` — bug fix
   - `refactor` — code change without behavior change
   - `chore` — config, deps, tooling
   - `docs` — documentation only
   - `test` — adding or updating tests
   - `style` — formatting, no logic change
3. Identify the scope (component, module, or area affected)
4. Write subject line: max 72 chars, imperative mood

## Format
```
<type>(<scope>): <short description>

<optional body — what changed and why, not how>

<optional footer — closes #issue, breaking changes>
```

## Examples
```
feat(auth): add JWT refresh token rotation

fix(dashboard): resolve null pointer on empty transactions list

chore(deps): upgrade Angular to 19.2.1

refactor(user-service): extract email validation to shared util

docs(readme): add Capacitor Android setup instructions
```

## Rules
- No period at end of subject line
- Body explains WHY, not WHAT
- Breaking changes: add `BREAKING CHANGE:` in footer
