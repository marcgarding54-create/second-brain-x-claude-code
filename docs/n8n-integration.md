# n8n Integration — The Automation Layer

## The Core Question

When you start working with AI-powered development, you inevitably hit this question:

> "Should I build this as a Claude workflow — or as an n8n automation?"

Most developers treat this as an either/or decision. This framework treats it as a **both** — with clear rules for which tool handles what.

---

## The Decision Framework

### Use Claude Code when:
- The task requires judgment, reasoning, or complex logic
- You need to write and debug custom code
- It's a one-time task or interactive session
- The requirements are ambiguous and need exploration
- Architecture decisions or planning are involved

### Use n8n when:
- The task should run **without you** — scheduled, triggered, or ongoing
- It's a recurring process (daily, hourly, on-event)
- It connects two or more SaaS tools with minimal logic
- The final phase of a project is "now make this automatic"
- You need a webhook endpoint that processes incoming data

### The pattern that appears constantly:
A project built with Claude Code ends with a phase: *"Now make this run automatically."* That handoff — from Claude Code to n8n — is exactly what the n8n Creator skill handles.

---

## The n8n Creator Skill

The `n8n-creator.skill.md` in this framework is not a simple helper. It's a complete automation execution channel with a full deployment pipeline:

```
Requirements
    ↓
Workflow Architecture (choose pattern)
    ↓
Node Discovery (MCP: search + configure)
    ↓
Iterative Build (create → update → validate)
    ↓
Pre-deployment Validation
    ↓
Live Deployment + Activation
    ↓
Documentation (JSON saved to project)
```

The agent handles all of this in one session. You describe what you want automated, and it comes back with a live, running workflow.

---

## The 5 Workflow Patterns

Every n8n workflow fits one of five patterns:

### 1. Webhook Processing
```
Webhook → Validate → Transform → Respond / Notify
```
**When:** Receiving events from external systems — form submissions, payment notifications, GitHub hooks, Slack commands.

### 2. Scheduled Task
```
Schedule → Fetch → Process → Deliver → Log
```
**When:** Reports that run daily, data syncs every hour, monitoring checks every 15 minutes.

### 3. HTTP API Integration
```
Trigger → HTTP Request → Transform → Action → Error Handler
```
**When:** Fetching from an API and doing something with the data — push to database, send notification, update a record.

### 4. AI Agent Workflow
```
Trigger → AI Agent (Model + Tools + Memory) → Output
```
**When:** AI-powered automations — intelligent routing, content generation pipelines, automated analysis.

### 5. Database Operations
```
Schedule → Query → Transform → Write → Verify
```
**When:** ETL tasks, cross-database syncs, data cleanup jobs.

---

## Sub-Skills

The n8n Creator ships with 7 specialized sub-skills that it loads when needed:

| Sub-skill | Purpose |
|-----------|---------|
| `n8n-workflow-patterns` | 5 proven architectural patterns with examples |
| `n8n-mcp-tools-expert` | How to use MCP tools correctly (nodeType formats, common mistakes) |
| `n8n-validation-expert` | Interpreting validation errors, fix strategies |
| `n8n-node-configuration` | Operation-specific node requirements |
| `n8n-expression-syntax` | `{{ }}` expressions, `$json`, `$node`, `$vars` |
| `n8n-code-javascript` | Code Node JavaScript best practices |
| `n8n-code-python` | Code Node Python best practices |

---

## Setup

### 1. n8n Instance

You need a running n8n instance. Options:
- **Self-hosted:** n8n on a VPS, Hetzner, Railway, Render
- **n8n Cloud:** n8n.io managed service
- **Local:** n8n running locally for development

### 2. API Credentials

In your n8n instance:
1. Go to Settings → API
2. Generate an API key
3. Note your instance URL

### 3. MCP Server Configuration

Add to your Claude Code MCP configuration:

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

> Store credentials in your environment, never in git-versioned files.

### 4. Verify Connection

Ask Claude: *"Check n8n health"* — it will run `n8n_health_check()` and confirm connectivity.

---

## Real-World Example

**Scenario:** You've built a newsletter tool with Claude Code. Now you want it to run automatically every Monday at 8am, pull the latest content, and send it.

**Without this framework:** You'd write a cron job, deploy it somewhere, manage it manually.

**With the n8n Creator:**

1. Tell Claude: *"Automate the newsletter: every Monday 8am, fetch content from [source], generate with Claude, send via [email tool]."*
2. The n8n Creator designs a Scheduled Task workflow
3. Searches for the right nodes (Schedule Trigger, HTTP Request, AI node, email node)
4. Builds and validates iteratively
5. Deploys to your n8n instance
6. Activates — running immediately

The newsletter now runs 24/7 without you touching it.

---

## Workflow Documentation

After every deployed workflow, the n8n Creator saves:
- Workflow JSON to `projects/[name]/docs/workflows/`
- Summary of what was built and why

This means you always have a recoverable backup and clear documentation for every automation in your system.

---

## The Bigger Picture

This framework answers the "Claude or n8n?" question permanently:

- **Claude Code** is your thinking and building partner — interactive, flexible, intelligent.
- **n8n** is your execution engine — reliable, 24/7, no-touch.
- **The n8n Creator** is the bridge — it lets Claude Code hand off work to n8n seamlessly.

You stop choosing between tools. You start using each for what it's actually good at.
