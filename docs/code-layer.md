# Code Layer — Deep Dive

## What It Is

The code layer is a Claude Code workspace with pre-configured rules, a Knowledge Base, and a skill system. It handles execution: writing code, running tests, deploying, debugging.

## Workspace Structure

- `CLAUDE.md` — Root configuration. Defines behavior, model strategy, golden rules.
- `.claude/rules/` — Modular behavior rules. Loaded automatically by Claude Code.
- `knowledge-base/` — Technical long-term memory. Indexed.
- `agents/` — Subagent definitions for complex workflows.
- `projects/` — Active project directories, each with its own CLAUDE.md.
- `skills/` — Reusable skill definitions.

## The Rules System

`.claude/rules/` files are loaded automatically. Three files by default:

1. `general-behavior.md` — High-level behavior principles
2. `knowledge-usage.md` — KB protocol (when to read, when to write)
3. `subagent-defaults.md` — Model selection and subagent patterns

## Knowledge Base Protocol

Every project contributes to the KB:
- Errors solved → `knowledge-base/[domain]/errors.md`
- Patterns discovered → `knowledge-base/[domain]/patterns.md`
- Configs proven → `knowledge-base/[domain]/templates.md`

The INDEX is the entry point. Update it every time you add a file.

## Subagent Strategy

Complex tasks use the wave execution pattern:
1. Orchestrator (main context) plans and coordinates
2. Independent tasks run in parallel in fresh subagent contexts
3. Results merge back into main context
4. Sequential tasks run in order between waves

This keeps the main context clean and enables parallel execution.
