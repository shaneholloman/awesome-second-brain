# Set Up Membase

## What You Are Building

A shared Memory + Wiki layer that your AI agents can read and write through MCP or supported plugins. The first useful workflow is:

```text
agent conversation -> add_memory/search_memory -> shared Memory
stable docs/specs/notes -> add_wiki/search_wiki -> Knowledge Wiki
```

## Choose This If

- You want memory across multiple AI tools quickly.
- You do not want to host a database, vector store, or MCP server.
- You want personal context and factual knowledge separated.
- You want app context such as chat history, Gmail, Calendar, Slack, or Obsidian vaults to feed one shared layer.

## Avoid This If

- You require local-only storage or full self-hosting.
- You need to customize graph construction, embedding jobs, or retrieval internals.
- You are evaluating a bounded research corpus where NotebookLM-style source notebooks are enough.

## Prerequisites

- Accounts: Membase account.
- Local runtime: Node.js/npm for CLI-based client installers.
- Agent clients: one supported client such as Claude, Claude Code, Codex, Cursor, VS Code, OpenCode, OpenClaw, Hermes, Gemini CLI, ChatGPT, or any MCP-compatible client.
- API keys: none for basic OAuth MCP setup.
- Storage: hosted by Membase.

## Setup Time

Official: under 5 minutes for the first connected agent.

## Install / Connect

1. Create an account at https://app.membase.so/.
2. Open the dashboard and go to Agents.
3. Pick your agent and use the generated one-click or CLI setup.

Generic MCP endpoint:

```text
https://mcp.membase.so/mcp
```

Codex setup:

```bash
npx -y membase@latest --client codex
```

Claude Code plugin setup:

```bash
claude plugin marketplace add aristoapp/claude-membase
claude plugin install membase@membase-plugins
```

Then in Claude Code:

```text
/reload-plugins
/membase:login
```

## Data-Source Setup

Start with agent memory first. Tell the connected agent durable context such as preferences, active projects, constraints, or decisions. The agent should call `add_memory`.

Then add factual knowledge:

- Use `add_wiki` for stable docs, specs, or reference notes.
- Import an Obsidian vault when you want linked markdown to become Wiki material.
- Connect external sources such as Gmail, Calendar, and Slack from the dashboard when available for the account.
- Import chat history from supported AI tools to bootstrap Memory.

## Agent Connection

Verify that the connected client can see Membase tools. The core MCP tools include:

- `add_memory`
- `search_memory`
- `get_current_date`
- `add_wiki`
- `search_wiki`
- `update_wiki`
- `delete_wiki`

Useful read-only resources include `membase://profile` and `membase://recent`.

## Verification

Ask the agent:

```text
Remember that I prefer TypeScript, Bun, and concise engineering explanations.
```

Then start a new session or use another connected agent and ask:

```text
What package manager do I prefer for TypeScript projects?
```

A working setup should call `search_memory` and use the saved preference. For Wiki, add a short reference note and ask a factual question that should call `search_wiki`.

## Known Failure Modes

- MCP configured but not authenticated.
- Agent has the tool but does not call it unless prompted or instructed.
- User stores factual documents as personal memories instead of Wiki entries.
- Imported raw context is available but still needs cleanup or source review.
- Team governance, export, and deletion requirements need plan-specific verification.

## Sources

- [Membase overview](https://docs.membase.so/)
- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Membase MCP](https://docs.membase.so/features/membase-mcp)
