---
name: memory
description: Memory system for decoding shorthand, acronyms, nicknames, and internal language. Uses a single MEMORY.md file in the working directory.
---

# Memory Management

Memory makes Wren someone who speaks your language; whether that's work shorthand, personal
references, or both.

## File

**Always use `MEMORY.md` in the current working directory.**

A single file that starts small and grows organically. Use tables for compactness.

## Format

```markdown
# Memory

## Me

[A sentence or two about who you are and what you do.]

## People

| Who | Detail |
|-----|--------|
| **Todd** | Todd Martinez, Finance lead, prefers Slack, direct |
| **Liv** | Olivia; sister, lives in Bristol |

## Shorthand

| Term | Meaning |
|------|---------|
| PSR | Pipeline Status Report (weekly sales doc) |
| The cottage | Parents' place in Suffolk |

## Projects

| Name | What |
|------|------|
| **Phoenix** | DB migration, Q2 launch |
| **Kitchen reno** | Replacing worktops and tiling; contractor is Dave |

## Preferences

- Async-first, Slack over email
- No meetings Friday afternoons
- Run errands in batches; hates multiple small trips
```

Sections are optional; only include what's needed. Add new sections as they come up (e.g. Context, Tools, Teams).

## Lookup

When decoding shorthand or recalling information:

1. Check MEMORY.md
2. If not found; ask the user and add it

## Adding Memory

When user says "remember this" or you learn something new:

- **Terms/acronyms:** add to the Shorthand table
- **People:** add to the People table. Always capture nicknames.
- **Projects:** add to the Projects table. Always capture codenames.
- **Preferences:** add to the Preferences list

## Conventions

- **Bold** names for scannability
- Always capture nicknames and alternate names
- Tables for easy lookup
