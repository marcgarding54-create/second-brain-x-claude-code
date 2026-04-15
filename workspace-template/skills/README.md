# Skills

Pre-built skill files for common development workflows. Each skill defines a specialized Claude Code agent.

## Available Skills

| Skill | Purpose | Trigger |
|-------|---------|---------|
| `security-agent.skill.md` | Security scanning, secret detection | Before git push, repo visibility changes |
| `qa-agent.skill.md` | Test runs, build validation, bug fixes | Before commits, after changes |
| `research-agent.skill.md` | Deep research with web search + docs | Stack decisions, unknown libraries |
| `frontend-specialist.skill.md` | UI components, Tailwind, responsive design | Frontend work |
| `solution-architect.skill.md` | Architecture decisions, infrastructure | Major design decisions |
| `backend-agent.skill.md` | Backend APIs, databases, server logic | Backend implementation |
| `supabase-agent.skill.md` | Supabase-specific development | Supabase projects |

## How to Use

Reference skills in your CLAUDE.md or invoke them directly:

```
Use the /security-agent skill to scan this before push.
```

## Creating New Skills

1. Copy an existing skill file as template
2. Define: name, description, triggers, model, instructions
3. Register in `00 Context/Tools.md` in your vault
4. Test with a real task
