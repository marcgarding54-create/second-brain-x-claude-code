# Agents

This folder contains subagent definitions — specialized Claude instances for specific task types.

## Agent File Convention

File naming: `[name].md`

```yaml
---
name: agent-name
model: sonnet
description: One sentence — what this agent does
---

# Agent Name

## Role
[What this agent is responsible for]

## Instructions
[Specific behavior, constraints, output format]

## Tools Available
[Which tools this agent uses]
```

## When to Create a New Agent

When you have a recurring task type that benefits from:
- Isolated context (no interference with main conversation)
- Specialized instructions
- Consistent behavior across sessions

## Pre-built Skills

See `skills/` folder for ready-to-use skill files that define agent behaviors.
