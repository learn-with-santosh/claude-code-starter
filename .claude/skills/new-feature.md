---
name: new-feature
description: Plan and scaffold a new feature end-to-end. Triggers on "add feature", "build", "implement", "create component", "new module", "scaffold".
allowed-tools: Read, Write, Bash, Glob
---

# New Feature Skill

## Process

### Step 1 — Understand
- What does this feature do?
- Who uses it and when?
- What are the acceptance criteria?

### Step 2 — Plan
Output a brief plan:
```
## Feature Plan: <name>

**What:** <one sentence>
**Files to create:** <list>
**Files to modify:** <list>
**Dependencies needed:** <npm packages if any>
```

### Step 3 — Scaffold
Create files in this order:
1. Types/interfaces first (`src/types/`)
2. Service/API layer
3. Component or controller
4. Route or template
5. Tests

### Step 4 — Verify
- Does it follow CLAUDE.md conventions?
- Is error handling in place?
- Are inputs validated?
- Is it tested?

## Angular 19 Feature Template
```
src/app/features/<feature-name>/
  <feature-name>.component.ts
  <feature-name>.component.html
  <feature-name>.component.scss
  <feature-name>.service.ts
  <feature-name>.routes.ts
```

## Node.js Feature Template
```
src/
  controllers/<feature>.controller.ts
  services/<feature>.service.ts
  models/<Feature>.ts
  routes/<feature>.routes.ts
  types/<feature>.types.ts
```
