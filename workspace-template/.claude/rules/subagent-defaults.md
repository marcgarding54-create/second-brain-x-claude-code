# Subagent Rules

## Model Hierarchy
- Orchestrator (main session): opus
- Standard subagents: model: sonnet (fast, cost-efficient)
- Research/analysis subagents: model: opus (only when complex)
- Simple tasks (search, format): model: haiku

## When to Use Subagents
- Parallel, independent sub-tasks
- Isolated context desired
- Different competency profiles needed

## Agent Definitions
Subagent definitions live in `agents/[name].md`.
Frontmatter must explicitly set `model:`.
