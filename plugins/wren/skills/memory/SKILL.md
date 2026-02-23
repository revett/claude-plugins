---
name: memory
description: Two-tier memory system that makes Claude a true workplace collaborator. Decodes shorthand, acronyms, nicknames, and internal language so Claude understands requests like a colleague would. memory/hot.md for working memory, memory/cold.md for the full knowledge base.
---

# Memory Management

Memory makes Claude your workplace collaborator - someone who speaks your internal language.

## The Goal

Transform shorthand into understanding:

```plaintext
User: "ask todd to do the PSR for oracle"
              ↓ Claude decodes
"Ask Todd Martinez (Finance lead) to prepare the Pipeline Status Report
 for the Oracle Systems deal ($2.3M, closing Q2)"
```

Without memory, that request is meaningless. With memory, Claude knows:

- **todd** → Todd Martinez, Finance lead, prefers Slack
- **PSR** → Pipeline Status Report (weekly sales doc)
- **oracle** → Oracle Systems deal, not the company

## Architecture

```plaintext
memory/
  hot.md    ← Working memory (~30 people, common terms, active projects)
  cold.md   ← Full knowledge base (everything, grows indefinitely)
```

**memory/hot.md (Working Memory):**

- Top ~30 people you interact with most
- ~30 most common acronyms/terms
- Active projects (5-15)
- Your preferences
- **Goal: Cover 90% of daily decoding needs**

**memory/cold.md (Full Knowledge Base):**

- Complete decoder ring - everyone, every term
- Rich detail: full profiles, project context, company info
- Searched when something isn't in hot.md
- Can grow indefinitely

## Lookup Flow

```plaintext
User: "ask todd about the PSR for phoenix"

1. Check memory/hot.md (working memory)
   → Todd? ✓ Todd Martinez, Finance
   → PSR? ✓ Pipeline Status Report
   → Phoenix? ✓ DB migration project

2. If not found → search memory/cold.md
   → Full knowledge base has everyone/everything

3. If still not found → ask user
   → "What does X mean? I'll remember it."
```

This tiered approach keeps hot.md lean (~100 lines) while supporting unlimited scale in cold.md.

## File Locations

- **Working memory:** `memory/hot.md`
- **Full knowledge base:** `memory/cold.md`

## Working Memory Format (memory/hot.md)

Use tables for compactness. Target ~50-80 lines total.

```markdown
# Memory (Hot)

## Me

[Name], [Role] on [Team]. [One sentence about what I do.]

## People

| Who | Role |
|-----|------|
| **Todd** | Todd Martinez, Finance lead |
| **Sarah** | Sarah Chen, Engineering (Platform) |
| **Greg** | Greg Wilson, Sales |

## Terms

| Term | Meaning |
|------|---------|
| PSR | Pipeline Status Report |
| P0 | Drop everything priority |
| standup | Daily 9am sync |

## Projects

| Name | What |
|------|------|
| **Phoenix** | DB migration, Q2 launch |
| **Horizon** | Mobile app redesign |

## Preferences

- 25-min meetings with buffers
- Async-first, Slack over email
- No meetings Friday afternoons
```

## Full Knowledge Base Format (memory/cold.md)

Everything that doesn't fit in hot.md. Grows over time.

```markdown
# Memory (Cold)

## People

### Todd Martinez

**Also known as:** Todd, T
**Role:** Finance Lead, **Team:** Finance, **Reports to:** CFO (Michael Chen)
- Prefers Slack DM, quick responses, very direct, best time: mornings
- Handles all PSRs and financial reporting
- Key contact for deal approvals over $500k
- Cubs fan, likes talking baseball

## Terms

### Acronyms

| Term | Meaning | Context |
|------|---------|---------|
| PSR | Pipeline Status Report | Weekly sales doc |
| OKR | Objectives & Key Results | Quarterly planning |
| P0/P1/P2 | Priority levels | P0 = drop everything |

### Internal Language

| Term | Meaning |
|------|---------|
| standup | Daily 9am sync in #engineering |
| the migration | Project Phoenix database work |
| ship it | Deploy to production |
| escalate | Loop in leadership |

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
- $1.2M budget, 6-month timeline. Critical path for Horizon project.

## Company Context

### Tools & Systems

| Tool | Used for | Internal name |
|------|----------|---------------|
| Slack | Communication | - |
| Asana | Engineering tasks | - |
| Salesforce | CRM | "SF" or "the CRM" |

### Teams

| Team | What they do | Key people |
|------|--------------|------------|
| Platform | Infrastructure | Sarah (lead) |
| Finance | Money stuff | Todd (lead) |

### Processes
| Process | What it means |
|---------|---------------|
| Weekly sync | Monday 10am all-hands |
| Ship review | Thursday deploy approval |
```

## How to Interact

### Decoding User Input (Tiered Lookup)

**Always** decode shorthand before acting on requests:

```plaintext
1. memory/hot.md   → Check first, covers 90% of cases
2. memory/cold.md  → Full knowledge base if not in hot
3. Ask user        → Unknown term? Learn it.
```

### Adding Memory

When user says "remember this" or "X means Y":

1. **Glossary items** (acronyms, terms, shorthand):
   - Add to memory/cold.md
   - If frequently used, also add to memory/hot.md

2. **People:**
   - Add/update in memory/cold.md (full detail)
   - Add to memory/hot.md People table if important
   - **Capture nicknames** - critical for decoding

3. **Projects:**
   - Add/update in memory/cold.md (full detail)
   - Add to memory/hot.md Projects table if active
   - **Capture codenames** - "Phoenix", "the migration", etc.

4. **Preferences:** Add to memory/hot.md Preferences section

### Recalling Memory

When user asks "who is X" or "what does X mean":

1. Check memory/hot.md first
2. Check memory/cold.md for full detail
3. If not found: "I don't know what X means yet. Can you tell me?"

### Progressive Disclosure

1. Read memory/hot.md for quick parsing of any request
2. Dive into memory/cold.md when you need full context for execution
3. Example: drafting an email to todd about the PSR
   - hot.md tells you Todd = Todd Martinez, PSR = Pipeline Status Report
   - cold.md tells you he prefers Slack, is direct, best time mornings

## Conventions

- **Bold** names in hot.md for scannability
- Keep hot.md under ~100 lines
- Always capture nicknames and alternate names
- Tables for easy lookup
- When something's used frequently, promote it to hot.md
- When something goes stale, remove from hot.md (keep in cold.md)

## What Goes Where

| Type | hot.md | cold.md |
| ------ | -------- | --------- |
| Person | Top ~30 frequent contacts | Full profiles for everyone |
| Acronym/term | ~30 most common | Complete list |
| Project | Active projects only | All projects with detail |
| Nickname | If in top 30 people | All nicknames |
| Company context | - | Tools, teams, processes |
| Preferences | All preferences | - |
| Historical/stale | ✗ Remove | ✓ Keep |

## Promotion / Demotion

**Promote to hot.md when:**

- You use a term/person frequently
- It's part of active work

**Demote from hot.md when:**

- Project completed
- Person no longer frequent contact
- Term rarely used

This keeps hot.md fresh and relevant.
