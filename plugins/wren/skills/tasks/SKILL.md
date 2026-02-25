---
name: tasks
description: Simple task management using a shared TASKS.md file. Reference this when the user asks about their tasks, wants to add/complete tasks, or needs help prioritising work.
---

# Task Management

- Tasks are tracked in a `TASKS.md` file in the current working directory
- Wren manages tasks, advises, and thinks alongside the user; it does not execute the work itself
  (e.g. don't go write a doc that's on the list)
- If TASKS.md doesn't exist, create it when first needed

## Format

Tasks are bullet lists grouped under **bold headings**. Groups are contextual; name them after the
context:

- Always leave a blank line between a heading and the first list item
- No checkboxes, no status tracking, no in-progress state
- No "Todo" heading; all tasks are implicitly todo
- Tasks are either on the list or removed when done; there is no "Done" section

### Task Syntax

```plaintext
- [!] Task title; context, for whom, due date [S]
```

**Priority (start of line):**

- `[!]` high
- unlabelled; normal
- `[~]` low

**Size (end of line):**

- `[S]` less than 30 minutes
- `[M]` 1-2 hours
- `[L]` half day or more

- Size and priority are optional
- Include "for [person]" for commitments and "due [date]" for deadlines
- Sub-bullets are not allowed

### Example

```markdown
# Tasks

## Work (People)

- [!] Reply to Todd about budget approval; he's waiting on sign-off [S]
- Prep slides for Monday all-hands; cover Q1 results [M]

## London Office

- [~] Book meeting room for Thursday; 3rd floor preferred [S]

## Personal

- Sort out home insurance renewal; due March 1 [L]
```

## How to Interact

**When user asks "what's on my plate" / "my tasks":**

- Read TASKS.md
- Summarise by group
- Highlight anything overdue or urgent

**When user says "add a task" / "remind me to":**

- Add to the appropriate group
- Include context if provided (who, due date)
- Ask which group if unclear
- Always assign a best guess priority based on context
- Don't leave everything at normal; make a call, the user can always correct it

**When user says "done with X" / "finished X":**

- Remove the task from the list entirely

**When suggesting what to work on next:**

Use a ranked numbered list of a few relevant tasks:

1. X; because...
2. Y; because...
3. Z; because...

## Reshaping the List

When adding or completing tasks, treat the whole file as alive:

- Rename, merge, or remove groups as the shape of work changes
- Update other tasks' titles, sizes, or priorities if new context warrants it
- Don't ask permission for housekeeping; just keep the list clean and current

## Extracting Tasks

When summarising meetings or conversations, offer to add extracted tasks:

- Commitments the user made ("I'll send that over")
- Action items assigned to them
- Follow-ups mentioned

Ask before adding; don't auto-add without confirmation.
