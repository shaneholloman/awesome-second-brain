# Set Up Mem0 / OpenMemory

## What You Are Building

A developer memory layer that can run through Mem0 Platform, open-source/self-hosted Mem0, SDKs, APIs, and MCP.

## Choose This If

- You are building an AI application and need programmable user/session/org memory.
- You want hosted memory now with a self-hosted option later.
- You want agents to save, search, update, and delete memories through MCP.

## Avoid This If

- You want a polished consumer second-brain app.
- You do not want to design memory scopes or retention policy.
- You mainly need static source-grounded research.

## Prerequisites

- Accounts: Mem0 Platform account for hosted setup.
- Local runtime: Node.js for MCP commands; Python or Node for SDK usage.
- API keys: Mem0 API key for hosted platform.
- Storage: hosted by Mem0 Platform, or self-hosted stack with local/managed components.
- Agent clients: Claude, Claude Code, Codex, Cursor, Windsurf, VS Code, OpenCode, or another MCP-compatible client.

## Setup Time

Official: minutes for hosted MCP or first SDK memory. Self-hosted setup is medium effort.

## Install / Connect

MCP setup:

```bash
npx mcp-add \
  --name mem0-mcp \
  --type http \
  --url "https://mcp.mem0.ai/mcp" \
  --clients "claude,claude code,cursor,windsurf,vscode,opencode"
```

For SDK usage, create an API key and run a first add/search loop with the Python or Node quickstart.

Self-hosting path:

```bash
make bootstrap
```

Use the self-hosted docs to configure LLM, embeddings, vector store, reranker, and providers.

## Data-Source Setup

Mem0 is API-first. Decide the memory scope before writing:

- `user_id` for durable user memory.
- `run_id` for session/task memory.
- organization or workspace memory for shared facts.
- metadata for filtering, governance, and deletion.

Write memory from your app, agent, MCP client, or integration code.

## Agent Connection

Expose Mem0 MCP to an agent and verify it can add, search, update, and delete memory. For apps, integrate the SDK and make memory operations explicit in the agent loop.

## Verification

Add:

```text
I am Alex and I prefer boutique hotels.
```

Search later:

```text
Any hotel preferences for Alex?
```

Verify the answer uses memory scoped to the expected `user_id` and, when relevant, `run_id`.

## Known Failure Modes

- Missing or wrong user/session identifiers.
- Over-broad organizational memory causing irrelevant recall.
- Sensitive information stored without consent, redaction, or governance.
- Self-hosted provider/vector-store defaults not aligned with privacy requirements.
- MCP installed but not actually called by the host agent.

## Sources

- [Mem0 Platform overview](https://docs.mem0.ai/platform/overview)
- [Mem0 MCP](https://docs.mem0.ai/platform/mem0-mcp)
- [Memory types](https://docs.mem0.ai/core-concepts/memory-types)
- [Mem0 open-source overview](https://docs.mem0.ai/open-source/overview)
