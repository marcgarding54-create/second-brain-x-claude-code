# Setup Guide

## Prerequisites

- [Obsidian](https://obsidian.md) installed
- [Claude Code](https://claude.ai/code) installed
- Git installed

## Step 1 — Clone the Repository

```bash
git clone https://github.com/[YOUR-USERNAME]/second-brain-x-claude-code.git
cd second-brain-x-claude-code
```

## Step 2 — Set Up the Vault

1. Open Obsidian
2. Click "Open folder as vault"
3. Select the `vault-template/` folder
4. The vault opens with the full structure

## Step 3 — Run Onboarding

1. Open `ONBOARDING.md` in Obsidian
2. Start a Claude chat in Obsidian (requires Claude plugin or API access)
3. Tell Claude: "Start onboarding"
4. Follow the guided setup (~10 minutes)

## Step 4 — Set Up the Workspace

1. Open a terminal
2. Navigate to `workspace-template/`
3. Open with Claude Code: `claude`

## Step 5 — Connect the Layers

Update `vault-template/00 Context/Tools.md`:
- Add the path to your workspace
- List your installed MCP servers
- Verify skills are listed

## Step 6 — First Session

Start a session in the vault: "What's in my inbox?" or create your first project.

## Optional: GitHub Integration

If you want to version your vault:

```bash
cd vault-template
git init
git add .
git commit -m "Initial vault setup"
gh repo create my-second-brain --private
git remote add origin [repo-url]
git push -u origin main
```

**Warning:** Your vault contains personal notes. Use a private repo.
