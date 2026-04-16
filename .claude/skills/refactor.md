---
name: refactor
description: Systematically improve code quality without changing behavior. Triggers on "refactor", "clean up", "improve code", "simplify", "optimize".
allowed-tools: Read, Write, Grep
---

# Refactor Skill

## Rules
- **Never change behavior** — only structure and readability
- Run tests before and after to confirm nothing broke
- One concern per refactor (don't mix cleanup with feature changes)

## Common Refactors

### Extract Function
Too-long function → split into smaller, named functions

### Remove Dead Code
Find and remove unused imports, variables, functions:
```bash
grep -r "import" src/ | grep -v "node_modules"
```

### Simplify Conditionals
```typescript
// Before
if (user !== null && user !== undefined && user.active === true) {}
// After
if (user?.active) {}
```

### Replace Magic Numbers
```typescript
// Before
if (status === 3) {}
// After
const STATUS_SUSPENDED = 3;
if (status === STATUS_SUSPENDED) {}
```

### Angular: Add OnPush
```typescript
@Component({
  changeDetection: ChangeDetectionStrategy.OnPush
})
```

## Output Format
```
## Refactor Plan — <file>

**Issues found:**
1. <issue> at line <n>
2. <issue> at line <n>

**Changes:**
- <what changed and why>

**Tests to run after:** <command>
```
