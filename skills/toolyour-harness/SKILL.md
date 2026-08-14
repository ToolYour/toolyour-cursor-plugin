---
name: toolyour-harness
description: Run ToolYour remote MCP jobs — SEO audits, security audits, and ship-gate — with plan → run → verify until pass.
---

Use the ToolYour MCP server already connected in this plugin.

## Loop

1. `plan_task` with the user's goal (free; does not execute).
2. `solve_task` or `run_playbook` to run the job.
3. Apply fixes in the workspace.
4. `verify_task` until the gate passes.

## Payload first

Pass workspace files as `input.text`, `input.code`, `input.html`, or `input.json`. Include a live URL only if the user asked to fetch a page, or the job cannot run without a fetch (PageSpeed, TLS, mixed content, live headers).

## Auth

Users need a ToolYour API key (`ty_…`) from https://www.toolyour.com/dashboard/api-keys  
Docs: https://www.toolyour.com/developers/mcp

Do not claim ToolYour replaces Cursor or that every catalog tool is on MCP. MCP exposes API-backed tools only. Free tier is 500 credits/month (tools cost 1–10 credits), not “500 requests.”
