---
name: debug
description: Diagnose errors, exceptions, and unexpected behavior. Triggers on "debug", "error", "exception", "not working", "broken", "fails", "crash".
allowed-tools: Read, Bash, Grep
---

# Debug Skill

## Process
1. Read the full error message and stack trace carefully
2. Find the exact file and line number
3. Read ±20 lines of surrounding code for context
4. Check recent git changes: `git log --oneline -10`
5. Form a root cause hypothesis
6. Suggest a targeted fix with explanation

## Output Format
```
## Debug Report

**Error:** <error type and message>
**Location:** <file>:<line>
**Root Cause:** <plain-English explanation>

**Fix:**
```<language>
<corrected code>
```

**Why this works:** <explanation>

**Verify with:** <command or test to confirm fix>
```

## Common Patterns

| Error | Likely Cause |
|---|---|
| `Cannot read properties of undefined` | Missing null check |
| `ECONNREFUSED 127.0.0.1:3000` | API server not running |
| `Module not found` | Wrong import path or case sensitivity |
| `CORS error` | Backend CORS config missing origin |
| `ExpressionChangedAfterItHasBeenChecked` | Angular CD issue, use `OnPush` or `async` pipe |
| `SequelizeDatabaseError` | SQL mismatch — check model vs actual schema |
| `JWT malformed` | Token not stripped of "Bearer " prefix |
| `NullInjectorError` | Angular service not provided in correct scope |
