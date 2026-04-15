# Second Brain × Claude Code

> A reproducible framework that turns Obsidian + Claude Code into a unified AI-powered system — for thinking, building, and shipping.

## What is this?

This framework combines two layers into one system:

**Vault Layer (Think & Plan)** — An Obsidian vault configured as an AI-powered Second Brain. Claude acts as your personal AI assistant (Claudian) — project manager, knowledge curator, thinking partner. This is your strategic layer.

**Code Layer (Build & Ship)** — A Claude Code workspace with Skills, Agents, and Rules pre-configured for development workflows. This is your operative layer.

**The combination is the product.** The vault plans and manages → Claude Code builds and delivers. Both sides know each other through a shared Knowledge Base and Skill Files.

## Quick Start

1. **Fork or clone** this repository
2. **Open `vault-template/`** in Obsidian as a new vault
3. **Open `workspace-template/`** in Claude Code
4. **Read `vault-template/ONBOARDING.md`** and let Claude walk you through setup (~10 minutes)
5. Start building

## Structure

```
second-brain-x-claude-code/
├── vault-template/      ← Open in Obsidian
├── workspace-template/  ← Open in Claude Code
└── docs/                ← Deep-dive documentation
```

## Key Features

- **Claudian** — Named AI identity for your vault. Consistent behavior, session routines, vault rules.
- **Onboarding Flow** — Interactive setup that personalizes the system to you in minutes.
- **Skill System** — Reusable agent definitions for common development tasks (security, QA, research, frontend, backend, Supabase, architecture).
- **Knowledge Base** — Structured long-term memory that persists across Claude Code sessions.
- **Session Routines** — Automatic daily notes, project status updates, and context management.

## Documentation

- [Philosophy](docs/philosophy.md) — Why this combination works
- [Setup Guide](docs/setup-guide.md) — Detailed setup instructions
- [Vault Layer](docs/vault-layer.md) — How the vault PM system works
- [Code Layer](docs/code-layer.md) — How the Claude Code workspace works
- [Skill System](docs/skill-system.md) — How Skills work and how to create new ones

## License

MIT — Fork, adapt, build on top.
