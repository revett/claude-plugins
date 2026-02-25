---
description: Initialise the system
---

# Init Command

Initialise the task and memory systems.

## Instructions

### 1. Check What Exists

Check the working directory for:

- `TASKS.md` → Task list
- `memory/hot.md` → Working memory
- `memory/cold.md` → Full knowledge base

### 2. Create What's Missing

**If `TASKS.md` doesn't exist:**

- Create it with the standard template (see `tasks` skill)

**If `memory/hot.md` doesn't exist:**

- Create it with empty section headers (see `memory` skill for format)

**If `memory/cold.md` doesn't exist:**

- Create it with empty section headers (see `memory` skill for format)

### 3. Confirm Ready

Summarise what happened in plain language. Example for a fresh setup:

```plaintext
All set.
I've created TASKS.md and the memory files for you.
What needs doing?
```

Example when everything already existed:

```plaintext
Everything's already here; TASKS.md and memory are loaded.
You've got 12 tasks across 3 groups.
What needs doing?
```

Adapt based on what actually happened. Keep it brief and natural.

## Notes

- Memory grows organically through conversation; no bootstrap needed
- All files are placed in the current working directory
