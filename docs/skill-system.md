# Skill System — How It Works

## What is a Skill?

A skill file is a reusable agent definition. It tells Claude Code how to behave when a certain type of task is triggered. Skills are the framework's way of encoding "how we do X" once, then invoking it consistently.

## Skill File Structure

```yaml
---
name: skill-name
description: One sentence — what this skill does
triggers: [keyword1, keyword2, scenario]
model: sonnet|haiku|opus
---

# Skill Name

## Purpose
When to use this skill.

## Instructions
What Claude should do.

## Output Format
What the output should look like.

## Rules
Constraints and non-negotiables.
```

## Pre-built Skills

The framework ships with seven skills:

| Skill | Best For | Model |
|-------|---------|-------|
| security-agent | Pre-push security scans | sonnet |
| qa-agent | Test runs, build validation | sonnet |
| research-agent | Stack decisions, library research | haiku |
| frontend-specialist | UI components, responsive design | sonnet |
| solution-architect | Architecture decisions (ADRs) | opus |
| backend-agent | APIs, databases, server logic | sonnet |
| supabase-agent | Supabase-specific development | sonnet |

## Creating a New Skill

1. Identify a repeated task pattern that would benefit from consistent behavior
2. Copy an existing skill file as template
3. Define: triggers, model, purpose, instructions, output format, rules
4. Save to `workspace-template/skills/[name].skill.md`
5. Register in vault `00 Context/Tools.md`
6. Test with a real task

## Model Selection Guide

- **haiku** — Fast lookups, simple transformations, research with many iterations
- **sonnet** — Most implementation tasks, balanced speed/quality
- **opus** — Complex reasoning, architecture decisions, multi-step analysis

## Skill Invocation

Skills are invoked in Claude Code via:
- Slash commands: `/security-agent`
- Natural language: "Use the security agent to scan this"
- CLAUDE.md rules: "Before every push, run the security-agent skill"
