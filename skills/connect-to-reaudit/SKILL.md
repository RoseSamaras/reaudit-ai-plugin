---
name: connect-to-reaudit
description: Connect Reaudit MCP via OAuth when the user says connect to Reaudit, connect reaudit, link reaudit, or set up reaudit mcp. Run codex mcp login — do not ask for API keys.
---

# Connect to Reaudit

Use this skill when the user wants to connect, link, or set up Reaudit MCP.

## Rules

1. **Never** tell the user to get an API key or edit config files unless OAuth fails twice.
2. **Always** run the terminal commands yourself when you have shell access.
3. Tell the user a browser window will open for OAuth — they must click **Authorize**.

## Codex CLI

```bash
codex mcp add reaudit --url https://mcp.reaudit.io/mcp
codex mcp login reaudit
```

After success:

```bash
codex mcp list
```

Confirm `reaudit` is authenticated, then offer `list_projects`.

If login fails:

```bash
codex mcp logout reaudit
codex mcp login reaudit
```

## Other clients

| Client | Action |
| --- | --- |
| Claude.ai / ChatGPT | Add connector `https://mcp.reaudit.io/mcp` → OAuth in UI |
| Claude Code | `claude mcp add --transport http reaudit https://mcp.reaudit.io/mcp` |
| Cursor | `cursor mcp add reaudit https://mcp.reaudit.io/mcp` |

## After connect

Tools may appear on the **next** turn. Ask the user to say "list my Reaudit projects" or run `/mcp`.

References: https://reaudit.io/auth.md · https://reaudit.io/connect
