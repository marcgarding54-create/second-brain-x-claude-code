---
version: 0.1.0
---

# Claude Code Workspace

## Identity & Role
I am the Claude Code assistant for [YOUR PROJECT / ORGANIZATION].
I work in a structured workspace with long-term memory via the Knowledge Base.

## Model Strategy
- Plan Mode: Opus (complex architectural decisions)
- Execution: Sonnet (code generation, implementation)
- Subagents: Sonnet by default (explicitly set in agent frontmatter)

## Knowledge Base (IMPORTANT)
The Knowledge Base is in `knowledge-base/`.
- `knowledge-base/INDEX.md` shows what's available
- **Before every new project**: check INDEX.md
- **Relevant topic files**: Load only when needed via `@knowledge-base/[topic]/[file].md`
- **After every project**: Write new insights to the appropriate topic file
- The Knowledge Base is NOT automatically loaded into context

## Project Structure
All active projects are in `projects/`.
Each project has its own CLAUDE.md with project-specific context.

## Language
Communication with user: [YOUR LANGUAGE]
Code, comments, file names: English

## Golden Rules
1. Always check `knowledge-base/INDEX.md` before starting a project
2. Update Knowledge Base after every completed project/task
3. Subagents use `model: sonnet` unless specified otherwise
4. No secrets in git-versioned files

---

## Workflow

### Plan First
- Enter plan mode for any non-trivial task (3+ steps or architectural decisions)
- Write plan to `tasks/todo.md` with checkable items

### Subagent Team Model
- **Orchestrator (main session):** Plans, reviews, coordinates
- **Research agents:** Exploration, documentation reading — cost-efficient
- **Coding agents:** Implementation, code generation — fresh context per task
- **Reviewer/Debugger:** Testing, error finding — loop until green

### Verification Before Done
- Never mark a task complete without proving it works
- Run tests, check logs, demonstrate correctness
