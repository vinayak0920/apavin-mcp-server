# Client configs

| Client | File | Where it goes |
|---|---|---|
| Cursor | [`cursor.mcp.json`](cursor.mcp.json) | `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project) |
| VS Code | [`vscode.mcp.json`](vscode.mcp.json) | `.vscode/mcp.json` in your project |
| Claude Code | [`claude-code.sh`](claude-code.sh) | Run it once in a terminal |
| Clients that only run local servers | [`mcp-remote.json`](mcp-remote.json) | The client's MCP config file |

Claude (claude.ai and Claude Desktop) and ChatGPT add remote servers from their settings screens, with the URL `https://mcp.apavin.com/mcp`. See the [main README](../README.md#connect-your-ai-app).

The first call opens Apavin in your browser to sign in and approve permissions. No API key goes in any of these files.
