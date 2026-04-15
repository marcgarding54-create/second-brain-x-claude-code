---
status: pending
---

# Onboarding — Personalize Your Second Brain

Welcome. This file guides you through setting up your vault in about 10 minutes.

**How it works:** Open this file in Obsidian with Claude active. Tell Claude: *"Start onboarding."* Claude will ask you a series of questions and update the vault files automatically.

---

## For Claude: Onboarding Instructions

When the user says "Start onboarding" or opens this file and asks to begin:

Run through the following steps in order. After each step, update the relevant files before moving to the next. Confirm each update with the user.

---

### Step 1 — Who Are You?

Ask the user:
1. What's your name?
2. What do you do professionally?
3. What's your main context / background in one sentence?
4. What are your top 2–3 goals for the next 6 months?
5. What language do you prefer to communicate in?

**Update after Step 1:**
- `00 Context/About Me.md` — Fill in name, profession, context, goals
- `CLAUDE.md` frontmatter — Update Owner, Language, Primary focus
- `CLAUDE.md` — Replace `[YOUR LANGUAGE]` with preferred language and instruction: "Respond in [language] when user writes in [language]"

---

### Step 2 — How Do You Work?

Ask the user:
1. How do you prefer responses? (concise/detailed, formal/casual)
2. Any communication preferences? (no filler phrases, no emojis, etc.)
3. How do you like to organize thoughts? (structured lists, flowing prose, etc.)

**Update after Step 2:**
- `00 Context/Writing Style.md` — Fill in communication preferences

---

### Step 3 — What Are Your Areas?

Ask the user:
- What are your 3–5 main areas of ongoing responsibility? (e.g. "Team Leadership", "Learning & Development", "Health", "Side Projects")

**Update after Step 3:**
- Create a folder for each area inside `03 Areas/`
- Create an `Overview.md` in each area folder with a brief description

---

### Step 4 — Active Projects

Ask the user:
- Do you have any active projects right now? (name + one sentence description each)

**Update after Step 4:**
- Create a project file in `02 Projects/` for each active project using `_template.md`
- Set status: active, date: today

---

### Step 5 — Tools & Integrations

Ask the user:
1. Are you using Claude Code alongside this vault?
2. Which MCP servers do you have active? (e.g. GitHub, Notion, Gmail, Calendar)
3. Any other tools that Claude should know about?

**Update after Step 5:**
- `00 Context/Tools.md` — Fill in available tools and integrations

---

### Onboarding Complete

After all steps:

1. Update this file's frontmatter: `status: completed`
2. Show the user a summary of what was set up
3. Suggest creating the first Daily Note
4. Mention: "Your vault is now personalized. The CLAUDE.md file is your main configuration — you can always update it as your system evolves."

---

## Manual Setup (Alternative)

If you prefer to set up manually without the interactive flow:

1. Edit `CLAUDE.md` — replace all `[PLACEHOLDER]` values
2. Edit `00 Context/About Me.md` — fill in your profile
3. Edit `00 Context/Tools.md` — list your available tools
4. Edit `00 Context/Writing Style.md` — describe your preferences
5. Create folders in `03 Areas/` for your areas of responsibility
6. Delete this ONBOARDING.md when done (or keep it as reference)
