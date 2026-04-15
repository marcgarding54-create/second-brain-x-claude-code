# Agent Skills

This folder contains skill files that define specialized agent behaviors for Claude Code.

## What is a Skill?

A skill file defines a specialized Claude Code agent — its purpose, capabilities, and instructions. Skills are stored in your Claude Code workspace under `skills/`.

## Skill File Convention

Skill files follow this naming pattern: `[name].skill.md`

Structure:
```yaml
---
name: skill-name
description: One sentence — what this skill does
triggers: [list of trigger keywords/commands]
model: sonnet|haiku|opus
---

# Skill Name

## Purpose
[What this skill does and when to use it]

## Instructions
[What Claude should do when this skill is triggered]

## Examples
[Example inputs and expected behavior]
```

## Available Skills

See your Claude Code workspace `skills/` folder for installed skills.

## Creating a New Skill

1. Identify a repeated task pattern
2. Create `[name].skill.md` in workspace `skills/`
3. Register it in `00 Context/Tools.md`
4. Test with a real task
