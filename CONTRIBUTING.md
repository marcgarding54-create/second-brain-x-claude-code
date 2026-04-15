# Contributing — How New Skills Flow Into the Framework

## The Update Cycle

This framework is designed to grow with you. Every time you build something new in your personal system — a new skill, an improved rule, a better workflow pattern — it can flow back into the framework and benefit everyone who uses it.

Here's exactly how that works.

---

## Scenario 1: You Built a New Skill

You were working on a project and created a new skill file (e.g. `stripe-agent.skill.md`, `email-writer.skill.md`, `data-analyst.skill.md`).

**Steps to contribute it:**

### 1. Generalize
Remove anything personal or environment-specific:
- Replace your n8n instance URL → `https://[your-n8n-instance]`
- Replace your domain/project names → `[YOUR PROJECT]`
- Replace personal file paths → generic placeholders
- Remove API keys, tokens, credentials (they should never be in files anyway)

### 2. English
Ensure all content is in English — comments, descriptions, instructions. The framework is international.

### 3. Check the skill file structure
```yaml
---
name: skill-name
description: One sentence — what this skill does
triggers: [trigger1, trigger2]
model: sonnet|haiku|opus
---

# Skill Name

## Purpose
## Instructions  
## Output Format
## Rules
```

### 4. Place it
Copy to `workspace-template/skills/[name].skill.md`

### 5. Register it
Add a row to `workspace-template/skills/README.md` skill table.

### 6. Update CHANGELOG
Add an entry under a new version:
```markdown
## [0.x.0] — YYYY-MM-DD

### Added
- `[name].skill.md` — [one sentence description]
```

### 7. Commit and push (or PR)
```bash
git add workspace-template/skills/[name].skill.md
git add workspace-template/skills/README.md
git add CHANGELOG.md
git commit -m "feat: add [name] skill — [one sentence description]"
git push
```

If contributing to someone else's fork of this framework: open a Pull Request instead.

---

## Scenario 2: You Improved an Existing Skill

You used a skill in production and found a better way — better validation logic, a new pattern, a mistake to avoid.

**Steps:**

1. Update the skill file in `workspace-template/skills/`
2. Note what changed in CHANGELOG under `### Changed`
3. Commit with: `fix: improve [skill-name] — [what changed and why]`

---

## Scenario 3: You Improved Vault or Workspace Structure

You changed your CLAUDE.md, added a rule file, improved the onboarding flow, or found a better session routine.

**Steps:**

1. Isolate the change — is it personal, or would everyone benefit?
2. Generalize (remove personal content, replace with placeholders)
3. Update the relevant template file
4. Test: would a new user understand this without context?
5. Commit with a clear message

---

## Scenario 4: You Have a New n8n Workflow Pattern

You built an n8n workflow that represents a new general pattern (beyond the 5 core patterns).

**Steps:**

1. Document the pattern in `docs/n8n-integration.md` under a new section
2. Optionally add reference details to `workspace-template/skills/n8n-creator.skill.md`
3. Remove any instance-specific details (URLs, credentials, personal node names)

---

## What Makes a Good Contribution

**Good:**
- Solves a real problem you encountered in production
- Works without any personal setup
- Has clear triggers — when should someone use this?
- Includes rules — what should never happen?

**Not yet ready:**
- Contains personal references (names, domains, URLs)
- Requires specific infrastructure that isn't documented
- Only works for one very specific use case with no generalizable value

---

## Version Numbering

This project follows [Semantic Versioning](https://semver.org/):

- **Patch** `0.x.Y` — Bug fixes, small improvements to existing skills/docs
- **Minor** `0.X.0` — New skills, new documentation, new features
- **Major** `X.0.0` — Breaking structural changes (rename folders, change file formats, etc.)

---

## Personal vs. Framework Repository

A common setup: you have your own fork with personal customizations, and you maintain it separately from this upstream framework.

**Recommended workflow:**

```
upstream: second-brain-x-claude-code (this repo)
origin:   your-fork (your personal version)
```

When you want to pull improvements from upstream:
```bash
git fetch upstream
git merge upstream/master
```

When you want to contribute back to upstream:
1. Make a clean branch with only the generalizable change
2. Open a Pull Request to this repository

This keeps your personal customizations separate while allowing you to contribute improvements and receive updates.
