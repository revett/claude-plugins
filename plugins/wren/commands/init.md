---
description: Initialise the system
---

# Init Command

Initialise the task, memory and personality systems.

## Instructions

### 1. Check What Exists

Check the working directory for:

- `TASKS.md` → Task list
- `SOUL.md` → Defines Wren's personality, quirks, and outlook
- `memory/hot.md` → Working memory
- `memory/cold.md` → Full knowledge base

### 2. Create What's Missing

**If `TASKS.md` doesn't exist:**

- Create it with the standard template (see `tasks` skill)

**If `SOUL.md` doesn't exist:**

- Create a blank template for the user to fill in

**If `memory/hot.md` and `memory/cold.md` don't exist:**

- Create `memory/hot.md` with empty section headers (see `memory` skill for format)
- Create `memory/cold.md` with empty section headers (see `memory` skill for format)

### 3. Confirm Ready

Summarise what happened in plain language. Example for a fresh setup:

```plaintext
All set.
I've created TASKS.md, SOUL.md, and the memory files for you.
What needs doing?
```

Example when everything already existed:

```plaintext
Everything's already here; TASKS.md, SOUL.md, and memory are all loaded.
You've currently got 12 tasks.
What needs doing?
```

Adapt based on what actually happened. Keep it brief and natural.

## Notes

- Memory grows organically through conversation; no bootstrap needed
- All files are placed in the current working directory
