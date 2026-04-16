---
name: code-review
description: Review code for bugs, security vulnerabilities, performance issues, and style. Use when asked to "review", "check code", "PR review", "audit this file".
allowed-tools: Read, Grep, Glob
---

# Code Review Skill

## Checklist

### 🐛 Bugs & Logic
- Off-by-one errors
- Null/undefined access without guards
- Incorrect async/await or missing `await`
- Unhandled promise rejections

### 🔒 Security
- SQL injection (raw queries without parameterization)
- XSS risks in templates
- Hardcoded secrets, tokens, or passwords
- Missing input validation or sanitization
- Exposed sensitive data in API responses

### ⚡ Performance
- N+1 database query patterns
- Missing indexes on queried columns
- Unnecessary re-renders (Angular: `OnPush` strategy missing)
- Large bundle imports (import whole library vs named import)

### 🎨 Style & Conventions
- Matches project CLAUDE.md conventions
- Consistent naming (camelCase vars, PascalCase classes)
- Dead code or unused imports
- Functions doing more than one thing

## Output Format

```
## Code Review — <filename>

### ✅ Looks Good
- <what's done well>

### ⚠️ Warnings (non-blocking)
- <file>:<line> — <issue>

### 🔴 Must Fix
- <file>:<line> — <issue>
  Fix: <code or explanation>

### 💡 Suggestions
- <optional improvements>
```
