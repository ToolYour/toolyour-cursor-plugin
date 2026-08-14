# ToolYour Cursor plugin

Cursor plugin that connects to the **ToolYour remote MCP harness**: plan → run → verify until pass.

Jobs: SEO audits, security audits, ship-gate. Same API key and monthly credits as [ToolYour REST](https://www.toolyour.com/developers).

- Setup: https://www.toolyour.com/developers/mcp
- Endpoint: `https://api.toolyour.com/mcp`
- Auth: `X-Api-Key: ty_…` from the [dashboard](https://www.toolyour.com/dashboard/api-keys)
- Smithery listing (optional): https://smithery.ai/servers/abdulwahabraza0000/toolyour-mcp-server

This repo is **not** the MCP server. The server stays at `api.toolyour.com`. This package is only the Cursor plugin + MCP client config.

## Install (after it is listed)

1. Open [cursor.directory](https://cursor.directory) and search **ToolYour**, or use **Add to Cursor** on the listing.
2. Create a key at https://www.toolyour.com/dashboard/api-keys
3. Set `TOOLYOUR_API_KEY` in your environment, **or** in Cursor **Customize → MCP → toolyour** add header:

```text
X-Api-Key: ty_YOUR_KEY
```

Do not commit a real key.

## Local test before submit

1. Copy this folder to `~/.cursor/plugins/local/toolyour` (Windows: `%USERPROFILE%\.cursor\plugins\local\toolyour`)
2. Reload Cursor (**Developer: Reload Window**)
3. Confirm **toolyour** under Customize → MCP / Plugins

## Submit

Repo is **https://github.com/ToolYour/toolyour-cursor-plugin** (public). Then:

1. **Primary listing:** https://cursor.directory/plugins/new — sign in, paste the GitHub URL, submit.
2. **Optional official store:** https://cursor.com/marketplace/publish — same repo; review can take days.

## Push to a new GitHub repo

From this directory (after you create an empty public repo):

```bash
git init
git add .
git commit -m "Initial ToolYour Cursor plugin (MCP harness)."
git branch -M main
git remote add origin https://github.com/ToolYour/toolyour-cursor-plugin.git
git push -u origin main
```

## Layout

| File | Why |
|------|-----|
| `plugin.json` | Agent Plugins manifest |
| `.cursor-plugin/plugin.json` | Cursor Marketplace manifest |
| `mcp.json` | Portable MCP (no secrets in headers) |
| `.mcp.json` | cursor.directory auto-detect + `TOOLYOUR_API_KEY` |
| `skills/toolyour-harness/SKILL.md` | plan → run → verify |

## License

MIT
