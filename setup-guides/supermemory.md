# Set Up Supermemory

## What You Are Building

A hosted cross-tool memory layer connected to AI clients through MCP, with optional API-key auth, project scoping, SDK usage, and external connectors.

## Choose This If

- You want a memory API and MCP server for multiple AI tools.
- You want documented connectors for Drive, Gmail, Notion, OneDrive, GitHub, or web crawling.
- You want project scoping for codebases or work contexts.

## Avoid This If

- You require local-first notes as the source of truth.
- You need a consumer-ready Memory/Wiki split rather than API-oriented memory.
- You need a user-operated dream loop.

## Prerequisites

- Accounts: Supermemory account.
- Local runtime: Node.js/npm for one-line MCP setup.
- Agent clients: Claude, Cursor, Windsurf, VS Code, or another MCP-compatible client.
- API keys: optional for API-key auth; OAuth is the default MCP path.
- Storage: hosted by Supermemory.

## Setup Time

Official: minutes for MCP connection.

## Install / Connect

Recommended OAuth setup:

```bash
npx -y install-mcp@latest https://mcp.supermemory.ai/mcp --client claude --oauth=yes
```

Replace `claude` with `cursor`, `windsurf`, `vscode`, or another supported MCP client.

Manual MCP config:

```json
{
  "mcpServers": {
    "supermemory": {
      "url": "https://mcp.supermemory.ai/mcp"
    }
  }
}
```

Optional API-key auth:

```json
{
  "mcpServers": {
    "supermemory": {
      "url": "https://mcp.supermemory.ai/mcp",
      "headers": {
        "Authorization": "Bearer sm_your_api_key_here"
      }
    }
  }
}
```

Optional project scoping:

```json
{
  "mcpServers": {
    "supermemory": {
      "url": "https://mcp.supermemory.ai/mcp",
      "headers": {
        "x-sm-project": "your-project-id"
      }
    }
  }
}
```

## Data-Source Setup

Use connectors when you want automatic document sync:

- Google Drive
- Gmail
- Notion
- OneDrive
- GitHub
- Web Crawler

Use the API/SDK path when your app should create, tag, or search memories directly.

## Agent Connection

After authentication, ask the agent to save a durable project convention and recall it from a new session. For scoped work, confirm the `x-sm-project` header is present so memories do not bleed across contexts.

## Verification

Ask:

```text
Save that this repo uses Bun and prefers explicit source-backed documentation.
```

Then ask:

```text
What package manager and documentation style should I use for this repo?
```

For connectors, create or update a known document in a connected source and verify it appears in Supermemory search after sync.

## Known Failure Modes

- OAuth not completed.
- API key header configured incorrectly.
- Project scoping omitted, causing unrelated memories to mix.
- Connector sync can be delayed or blocked by OAuth permissions.
- Disconnect/delete behavior differs by connector and must be reviewed before removing sources.

## Sources

- [Supermemory MCP](https://supermemory.ai/mcp/)
- [Supermemory MCP setup](https://supermemory.ai/docs/supermemory-mcp/setup)
- [Supermemory connectors](https://supermemory.ai/docs/connectors/overview)
