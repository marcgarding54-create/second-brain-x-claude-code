# Setup Guide

Complete setup in ~15 minutes. You need a Claude subscription (Pro or above) to use Claude Code and Claudian.

---

## Step 1 — Create Your Folder

Create a dedicated folder that will become your vault and workspace. Choose a name that fits:

```bash
# macOS / Linux
mkdir ~/Second\ Brain

# or
mkdir ~/ProjectManager
```

```powershell
# Windows (PowerShell)
mkdir "$HOME\Second Brain"
```

---

## Step 2 — Install Claude CLI

Claude Code is the command-line tool that powers Claudian inside Obsidian.

**Prerequisites:** Node.js 18+. Install from [nodejs.org](https://nodejs.org) if you don't have it.

```bash
npm install -g @anthropic-ai/claude-code
```

**Verify:**
```bash
claude --version
```

**Log in with your Anthropic account:**
```bash
claude
```

The first run opens a browser window. Complete the login and return to the terminal. You only need to do this once.

---

## Step 3 — Configure the Filesystem MCP

The Filesystem MCP server allows Claude to actively read and write files in your vault. Without it, Claudian can only see what you paste into the chat — with it, Claude navigates, edits, and manages your vault directly.

Open (or create) your Claude config file:

| OS | Path |
|----|------|
| macOS / Linux | `~/.claude/settings.json` |
| Windows | `%APPDATA%\Claude\settings.json` |

Add the following — replace the path with your folder from Step 1:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/Users/yourname/Second Brain"
      ]
    }
  }
}
```

> **Tip:** You can add multiple paths to the args array to grant Claude access to additional directories (e.g. a separate workspace folder).

**Verify the MCP is active:**
```bash
claude mcp list
```
You should see `filesystem` in the list.

---

## Step 4 — Install Obsidian

Download and install Obsidian from [obsidian.md](https://obsidian.md).

Obsidian is free for personal use. No account required.

---

## Step 5 — Open Your Vault

1. Open Obsidian
2. Click **"Open folder as vault"**
3. Select the folder you created in Step 1

Your vault is now open and empty — that's correct. The onboarding in Step 8 will set everything up.

---

## Step 6 — Install the BRAT Plugin

BRAT lets you install Obsidian plugins directly from GitHub — including Claudian, which is not yet in the official directory.

1. In Obsidian, open **Settings** (gear icon, bottom left)
2. Go to **Community plugins**
3. Disable **Restricted mode** if prompted
4. Click **Browse** and search for **BRAT**
5. Install and **Enable** BRAT

---

## Step 7 — Install Claudian via BRAT

Claudian embeds Claude Code as an AI collaborator directly in your vault sidebar.

1. Click the **BRAT icon** in the left ribbon
2. Choose **"Add a beta plugin for testing (with or without version)"**
3. Enter the repository URL:
   ```
   https://github.com/YishenTu/Claudian
   ```
4. Check **"Enable after installing the plugin"**
5. Click **Add Plugin**

Confirm Claudian is enabled under **Settings → Community plugins**.

**First-time login:** Claudian will prompt you to log in with your Anthropic account on first use. Use the same account from Step 2.

---

## Step 8 — Start Onboarding

Open the Claudian chat (sidebar icon or `Ctrl/Cmd + P` → "Claudian: Open Chat") and send this message:

```
Hello Claude. Please install this repository into my vault and run the onboarding:
https://github.com/marcgarding54-create/second-brain-x-claude-code
```

Claude will:
1. Clone the repository
2. Copy the vault template into your vault
3. Walk you through 5 personalization questions (~10 minutes)
4. Create your `CLAUDE.md`, context profile, active projects, and areas

> **Need help?** Tell Claude at any point: *"I'm stuck — guide me through the next step proactively."*

---

## Optional: Connect the Workspace Layer

The `workspace-template/` folder contains the Claude Code workspace with 8 pre-built agent skills. This is for running Claude Code in a terminal alongside your vault.

```bash
cd ~/Second\ Brain/workspace-template
claude
```

Claude reads `CLAUDE.md` and all `.claude/rules/` files on startup. Type `/research-agent` or `/n8n-creator` to activate a skill.

---

## Optional: n8n Integration

Connect your n8n instance to enable automated workflow deployment from Claude Code.

Add to your Claude config (`~/.claude/settings.json`):

```json
{
  "mcpServers": {
    "n8n": {
      "command": "npx",
      "args": ["-y", "n8n-mcp"],
      "env": {
        "N8N_API_URL": "https://your-n8n-instance.com",
        "N8N_API_KEY": "your-api-key"
      }
    }
  }
}
```

---

## Troubleshooting

**`claude: command not found` after install:**
```bash
export PATH="$PATH:$(npm root -g)/.bin"
# Add this line to your ~/.bashrc or ~/.zshrc to make it permanent
```

**Claudian shows authentication error:**
Run `claude` in terminal to re-authenticate, then restart Obsidian.

**Filesystem MCP not listed (`claude mcp list` shows empty):**
Check that `~/.claude/settings.json` is valid JSON and the path exists exactly as written (paths are case-sensitive on macOS and Linux).

**BRAT doesn't find Claudian:**
Make sure you entered the URL exactly as `https://github.com/YishenTu/Claudian` (capital C in Claudian).
