---
name: n8n-creator
description: Design, build, validate, and deploy complete n8n automation workflows directly via MCP — from requirements to live deployment in one session
triggers: [n8n, automation, workflow, automate, recurring task, schedule, webhook, integrate, n8n workflow, deploy workflow]
model: sonnet
---

# n8n Creator

## Purpose

The n8n Creator is the automation execution channel of this framework. When a task is recurring, scheduled, event-driven, or fits the "run-without-me" model — build it in n8n, not in code.

**The decision framework:**

| Task type | Use |
|-----------|-----|
| 24/7 recurring tasks (schedules, webhooks, triggers) | **n8n** |
| Integrations between SaaS tools (no custom logic) | **n8n** |
| Complex business logic, analysis, custom code | **Claude Code** |
| One-time tasks, research, planning | **Claude Code** |
| Project final phase: "make this run automatically" | **n8n via this skill** |

The combination is the point: Claude Code builds and thinks. n8n runs 24/7 without intervention. Together they cover the full spectrum.

---

## Capabilities

This skill can:
- Design workflow architecture from requirements
- Search for the right n8n nodes via MCP
- Configure nodes correctly (with validation)
- Build complete workflows iteratively
- Validate before deployment
- Deploy directly to your n8n instance
- Activate workflows for production

---

## Workflow: Requirements → Live

```
1. Understand requirements
   → What triggers this? What should happen? What's the output?

2. Choose workflow pattern
   → Webhook / Schedule / API Integration / AI Agent / Database

3. Search nodes via MCP
   → search_nodes({query: "..."})
   → get_node({nodeType: "nodes-base.name"})

4. Build iteratively
   → n8n_create_workflow({name, nodes, connections})
   → n8n_update_partial_workflow({id, operations: [...]})
   → Iterate every ~56 seconds (don't rush, validate between edits)

5. Validate
   → validate_node({nodeType, config, profile: "runtime"})
   → n8n_validate_workflow({id})
   → Fix errors → validate again (expect 2-3 cycles)

6. Deploy & activate
   → n8n_update_partial_workflow({operations: [{type: "activateWorkflow"}]})

7. Document
   → Save workflow JSON to project docs/
   → Update Knowledge Base with patterns learned
```

---

## Sub-Skills (load when needed)

These skills contain deep reference material. Load them via `@skills/[name]/` when building:

| Skill | Load When |
|-------|----------|
| `n8n-workflow-patterns` | Choosing architecture, designing structure |
| `n8n-mcp-tools-expert` | Using MCP tools effectively, nodeType formats |
| `n8n-validation-expert` | Interpreting validation errors |
| `n8n-node-configuration` | Operation-specific node requirements |
| `n8n-expression-syntax` | Writing `{{ }}` expressions, `$json`, `$node` |
| `n8n-code-javascript` | Code Node JavaScript best practices |
| `n8n-code-python` | Code Node Python best practices |

---

## The 5 Core Workflow Patterns

### 1. Webhook Processing
```
Webhook → Validate → Transform → Respond / Notify
```
Use for: Receiving events from external systems, form submissions, GitHub webhooks

### 2. Scheduled Task
```
Schedule → Fetch → Process → Deliver → Log
```
Use for: Daily reports, recurring syncs, periodic checks

### 3. HTTP API Integration
```
Trigger → HTTP Request → Transform → Action → Error Handler
```
Use for: Fetching data from APIs, syncing between services

### 4. AI Agent Workflow
```
Trigger → AI Agent (Model + Tools + Memory) → Output
```
Use for: AI-powered automations, intelligent routing, content generation pipelines

### 5. Database Operations
```
Schedule → Query → Transform → Write → Verify
```
Use for: ETL, data syncs, cross-database operations

---

## Critical: nodeType Format

Two formats — never mix them:

```javascript
// For search/validate tools:
"nodes-base.slack"
"nodes-base.httpRequest"

// For workflow creation/update tools:
"n8n-nodes-base.slack"
"n8n-nodes-base.httpRequest"

// search_nodes returns BOTH — use workflowNodeType for workflow tools
```

---

## MCP Setup Required

This skill requires the `n8n-mcp` MCP server configured with:
```
N8N_API_URL=https://[your-n8n-instance]
N8N_API_KEY=[your-api-key]
```

Without API credentials, you can still: search nodes, validate configs, browse 2700+ templates.

---

## Rules

- Always validate before deploying (`profile: "runtime"`)
- Build iteratively — never one-shot complex workflows
- Use `intent` parameter in every `n8n_update_partial_workflow` call
- After deployment: save workflow JSON to project `docs/workflows/`
- Update Knowledge Base with any new patterns discovered
- Never hardcode credentials in workflow nodes — use n8n credential store

---

## Output

After completing a workflow:
1. Live workflow URL on n8n instance
2. Workflow JSON saved to `docs/workflows/[name].json`
3. Brief summary: trigger, steps, what it does, any credentials needed
