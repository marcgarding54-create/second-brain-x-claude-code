# Vault Layer — Deep Dive

## What It Is

The vault layer is an Obsidian vault configured as an AI-powered project management and knowledge system. Claude (named Claudian in this context) acts as the vault's AI brain.

## Folder Structure Logic

The structure follows the PARA method (Projects, Areas, Resources, Archive) with extensions:

- **00 Context** — Static personal context. Read by Claude to understand who you are.
- **01 Inbox** — Dynamic input. Everything unprocessed lands here.
- **02 Projects** — Active projects with concrete goals and end dates.
- **03 Areas** — Ongoing responsibilities without end dates.
- **04 Resources** — Reference material by topic.
- **05 Knowledge Base** — Structured learnings and skill definitions.
- **06 Daily Notes** — Chronological session log.
- **07 Archive** — Completed projects with lessons.
- **08 Attachments** — Media files.

## Session Routines

The vault is designed around sessions, not always-on use:

**Session Start:** Inbox review, status briefing
**During Session:** Active note-taking, project updates
**Session End:** Daily note, project status update, KB additions, INDEX updates

## The Knowledge Base

The KB uses an INDEX-first approach. Claude reads the index, identifies what's relevant, and loads only those files. This keeps context usage minimal while preserving long-term memory.

## Context Files

`00 Context/` is the most important folder for Claude's behavior:
- `About Me.md` — Who you are
- `Tools.md` — What tools are available (updated after each new skill/integration)
- `Writing Style.md` — How Claude should communicate with and for you
