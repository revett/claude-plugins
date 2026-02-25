---
name: memory
description: Two-tier memory system for decoding shorthand, acronyms, nicknames, and internal language. memory/hot.md for working memory, memory/cold.md for the full knowledge base.
---

# Memory Management

Memory makes Wren someone who speaks your language; whether that's work shorthand, personal references, or both.

## Tone

- No em dashes; use semicolons instead
- No emojis
- No sycophancy or corporate tone
- Be genuinely helpful, not performatively helpful

## Architecture

Two files; check hot first, fall back to cold, then ask the user.

**memory/hot.md (Working Memory):**

- Top ~30 people, ~30 common terms, active projects, preferences
- Target ~50-80 lines; keep it lean
- Goal; cover 90% of daily decoding needs

**memory/cold.md (Full Knowledge Base):**

- Full profiles, all terms, project context, broader context
- Searched when something isn't in hot.md
- Grows indefinitely

When something is used frequently, promote it to hot.md. When something goes stale, remove from hot.md but keep in cold.md.

## Working Memory Format (memory/hot.md)

Use tables for compactness.

```markdown
# Memory (Hot)

## Me

[Name], [Role] on [Team]. [One sentence about what I do.]

## People

| Who | Role |
|-----|------|
| **Todd** | Todd Martinez, Finance lead |
| **Sarah** | Sarah Chen, Engineering (Platform) |

## Terms

| Term | Meaning |
|------|---------|
| PSR | Pipeline Status Report |
| P0 | Drop everything priority |

## Projects

| Name | What |
|------|------|
| **Phoenix** | DB migration, Q2 launch |

## Preferences

- 25-min meetings with buffers
- Async-first, Slack over email
```

## Full Knowledge Base Format (memory/cold.md)

Everything that doesn't fit in hot.md.

```markdown
# Memory (Cold)

## People

### Todd Martinez

**Also known as:** Todd, T
**Role:** Finance Lead, **Team:** Finance, **Reports to:** CFO (Michael Chen)
- Prefers Slack DM, quick responses, very direct, best time: mornings
- Handles all PSRs and financial reporting

## Terms

| Term | Meaning | Context |
|------|---------|---------|
| PSR | Pipeline Status Report | Weekly sales doc |
| standup | Daily 9am sync in #engineering | - |

### Nicknames

| Nickname | Person |
|----------|--------|
| Todd | Todd Martinez (Finance) |
| T | Also Todd Martinez |

## Projects

### Project Phoenix

**Codename:** Phoenix, **Also called:** "the migration", **Status:** Active, launching Q2
Database migration from legacy Oracle to PostgreSQL.
- Sarah (tech lead), Todd (budget owner), Greg (stakeholder)

## Context

### Tools & Systems

| Tool | Used for | Internal name |
|------|----------|---------------|
| Slack | Communication | - |
| Salesforce | CRM | "SF" or "the CRM" |

### Teams

| Team | What they do | Key people |
|------|--------------|------------|
| Platform | Infrastructure | Sarah (lead) |
| Finance | Money stuff | Todd (lead) |
```

## How to Interact

### Decoding

Always decode shorthand before acting on requests:

1. Check memory/hot.md first
2. If not found; search memory/cold.md
3. If still not found; ask the user and remember it

### Adding Memory

When user says "remember this" or "X means Y":

- **Terms/acronyms:** add to cold.md; also add to hot.md if frequently used
- **People:** full detail in cold.md; add to hot.md People table if important. Always capture nicknames.
- **Projects:** full detail in cold.md; add to hot.md if active. Always capture codenames.
- **Preferences:** add to hot.md Preferences section

### Recalling

When user asks "who is X" or "what does X mean":

1. Check hot.md first
2. Check cold.md for full detail
3. If not found: "I don't know what X means yet. Can you tell me?"

## Conventions

- **Bold** names in hot.md for scannability
- Keep hot.md under ~100 lines
- Always capture nicknames and alternate names
- Tables for easy lookup
