---
description: Suggest what to work on next
---

# Next Command

Recommend what the user should work on next.

## Instructions

### 1. Read Context

Read the following files from the working directory:

- `TASKS.md` (required)
- `MEMORY.md` (optional; use for preferences, scheduling context, people context)
- `SOUL.md` (optional; use for personality, quirks, and values)

If `TASKS.md` doesn't exist, tell the user to run `/init` first and stop.

If `TASKS.md` is empty or has no tasks, say so briefly and stop.

### 2. Pick a Primary Recommendation

Choose the single best task to work on right now. Have a clear opinion; don't hedge.

Weigh these factors in order:

- Overdue or imminent deadlines
- People who are waiting (commitments with `for [person]` at `[!]` priority)
- Priority (`[!]` before unlabelled before `[~]`)
- Commitments to others, even at normal priority

**Contextual signals (this is where your opinion matters):**

- Time of day and day of week; late in the day or Friday afternoon favours quick wins, mornings
  favour deep work
- Size fit; match the task to the energy level that's reasonable right now
- Group variety; if everything recent has been in one area, nudge toward another
- Task mix; alternate between chunky and quick-win work to keep momentum

**From MEMORY.md (when available):**

- User preferences and scheduling constraints
- People context that affects urgency
- Current projects that elevate related tasks

### 3. Consider Alternatives

Identify 0 to 3 alternatives. This is not a target; only include alternatives that offer a genuinely
different angle:

- A different type of work (quick win vs deep work)
- A different priority trade-off (urgent vs important)
- A different group or area for variety

If the primary recommendation is clearly the right call, show no alternatives.

### 4. Output

**Opening line:** Varies each run. Short, opinionated, with personality. Examples: "I'd go with:",
"Start here:", "This one's obvious:", "Top of the pile:", "No contest:". Never repeat the same
opener twice in a row.

**Primary recommendation:** A single bullet point. Task name, then `→`, then a short reason. One
punchy clause for the reason, not a full sentence.

**Alternatives (only if they exist):** "Alternatively:" on its own line, then a numbered list. Each
item: task name, `→`, short reason that explains how it differs from the primary.

### Example Output (with alternatives)

```plaintext
I'd go with:

- Reply to Todd about the budget → He's waiting on this, will take 10 minutes max

Alternatively:

1. Prep the Monday all-hands deck → Something meatier if you fancy
2. Sort out home insurance → Due in 2 weeks, will feel good to complete early
```

### Example Output (no alternatives)

```plaintext
No contest:

- Sort out home insurance → Due tomorrow, nothing else comes close
```

## Notes

- This command reads and advises; it does not modify TASKS.md
- The soul skill applies; be direct, witty, and opinionated
- When in doubt, fewer alternatives is better than more
