---
version: 0.1.0
---

# Vault Context

This vault is your Second Brain — managed by **Claudian**, your personal AI assistant built on Claude.

## About This Vault

> **Setup required:** Read [[ONBOARDING]] to personalize this vault for you. Until then, placeholder values like `[YOUR NAME]` appear throughout.

**Owner:** [YOUR NAME]  
**Language:** [YOUR LANGUAGE — e.g. English / Deutsch]  
**Primary focus:** [YOUR MAIN GOALS]

For the full profile, see [[00 Context/About Me]].

---

## Vault Structure

- **00 Context/** — Your personal context profile (About Me, Tools, Writing Style). Read this when creating content, writing emails, or formulating offers.
- **01 Inbox/** — Quick thoughts, brain dumps, unprocessed notes. Everything without a clear home lands here.
- **02 Projects/** — Active projects with a concrete goal and end date.
- **03 Areas/** — Ongoing areas of responsibility without end dates.
- **04 Resources/** — Reference material organized by topic.
- **05 Knowledge Base/** — Structured knowledge, Agent Skills, orchestration guides. **Always start with [[05 Knowledge Base/Knowledge Base]] (INDEX)** — read index first, then load targeted files.
- **06 Daily Notes/** — Daily log. Format: YYYY-MM-DD.md. Auto-sorted chronologically.
- **07 Archive/** — Completed projects. **Start with [[07 Archive/INDEX]]** — overview of all projects with lesson references.
- **08 Attachments/** — Images, PDFs, media. Obsidian stores all embedded files here automatically.

---

## Tools & Skills

Before any new project or task: **read [[00 Context/Tools]]**. All available Skills, MCP servers, and golden rules are listed there. Never plan from scratch when a tool already exists.

---

## Vault Rules

- Use wikilinks: [[Note Name]] for connections between notes
- New notes without a clear home go to 01 Inbox/
- Daily Notes format: YYYY-MM-DD.md
- Use YAML frontmatter: tags, status (active/completed/paused), date
- File names in normal writing with spaces: Descriptive Name.md
- New projects as single .md directly in 02 Projects/. Subfolders only if a project needs multiple files.
- Areas and Resources are always folders — they grow over time
- Completed projects move to 07 Archive/. Two triggers: (1) you say so directly, (2) project file has `status: completed` → archive at next session start
- Always ask before deleting or overwriting
- When you say "remember this" or "save this": write to the appropriate context file

---

## Session Routines

### At Session Start
1. Check 01 Inbox/ for new notes
2. Show what's there
3. Offer to sort entries into appropriate folders

### Context on Demand
When you ask "What's currently active?" or "Where was I?": Read the last 2–3 daily notes in 06 Daily Notes/ and active project files in 02 Projects/ → give a short briefing.

### At Session End (Required Routine)

**Always follow this order:**

1. **Create Daily Note** — `06 Daily Notes/YYYY-MM-DD.md` with:
   - What was done today
   - Active projects + current status
   - Open items / Next steps
   - Decisions made

2. **Update Project Files** — Bring status and next steps in `02 Projects/` up to date

3. **Save New Insights** — Update Knowledge Base and Lessons Learned if needed

4. **Update INDEX Files** — After every KB or Archive change:
   - `05 Knowledge Base/Knowledge Base.md` — new entry for every new/changed file
   - `07 Archive/INDEX.md` — new entry for every archived project
   - Rule: INDEX entry must be precise enough to understand the file content **without reading it**

**Why:** Every token in the chat history costs context. Everything important lives in the vault — the chat is just the work tool, not the memory. The INDEX files are the bridge: next session reads index → loads targeted files → starts with full knowledge, minimal context use.
