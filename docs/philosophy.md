# Philosophy — Why This Combination Works

## The Problem

Most developers have two separate, disconnected systems:
1. A note-taking app (Notion, Obsidian, Bear) for thinking and planning
2. A development environment (VS Code, terminal) for building

These systems don't talk to each other. Context lives in your head and degrades over time.

## The Solution: Two Layers, One System

This framework makes Obsidian and Claude Code aware of each other through a shared language:

- **The vault** knows about your projects, goals, and decisions
- **The workspace** knows about your code, patterns, and technical decisions
- **The Knowledge Base** bridges both — learnings from coding sessions flow back into the vault, and project context from the vault informs coding sessions

## Why Claude as the Bridge?

Claude Code runs in your workspace. Claudian (the same model) runs in your vault. When both are configured with the same context about you, your projects, and your system — they behave as one coherent assistant, not two separate tools.

## The Onboarding Insight

An empty template is just folders. The onboarding flow is what transforms it into *your* system. Five questions, ten minutes, and the vault becomes a reflection of how you actually work.

## The Skill System Insight

Skills are reusable agent definitions. Once you've defined how a security scan should work, you never think about it again — you just invoke the skill. The framework ships with eight pre-built skills covering the most common development workflows.

## The Third Layer: n8n

The question every AI developer eventually asks: *"Should I build this with Claude — or automate it with n8n?"*

The wrong answer is to choose. The right answer is to understand what each is good at:

- **Claude Code** is for work that requires judgment — complex logic, architecture decisions, debugging, analysis, anything interactive.
- **n8n** is for work that should disappear — recurring tasks, scheduled processes, event-driven integrations that run 24/7 without your attention.

The pattern that emerges constantly: a project built with Claude Code ends with the question *"now make this automatic."* That handoff is now handled by the n8n Creator skill — a full deployment pipeline from requirements to live workflow.

**Three tools, three roles, zero overlap.** The vault plans. Claude Code builds. n8n runs forever.
