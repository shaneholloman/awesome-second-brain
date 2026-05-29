# Set Up Cognee

## What You Are Building

A persistent knowledge graph memory setup exposed to MCP-compatible tools.

## Choose This If

- You want MCP access to structured memories.
- You want local standalone mode for personal development or API mode for shared memory.
- You want memory tools such as `remember`, `recall`, `forget_memory`, and `improve`.

## Avoid This If

- You want the lowest-friction hosted consumer memory.
- You cannot decide whether each client should have isolated or shared memory.
- You need a fully polished end-user notes UI.

## Prerequisites

- Accounts: none for local standalone; account/API details for shared API mode.
- Local runtime: Docker for quickstart or source build for local development.
- API keys: depends on cloud/API mode and configured model providers.
- Agent clients: Cursor, Claude Desktop, Continue, Cline, Roo Code, or another MCP-compatible client.
- Storage: managed by standalone MCP server or centralized Cognee backend.

## Setup Time

Official: minutes with Docker quickstart. Shared API mode requires additional account and backend configuration.

## Install / Connect

Choose one mode:

- Standalone mode: each MCP server manages its own database and processing.
- API mode: MCP connects to a centralized Cognee backend so multiple clients share a graph.

Use Docker quickstart for the first local test, then add the MCP server to the target client.

## Data-Source Setup

Start with a small project memory:

1. Ask the agent to `remember` a project rule.
2. Add a document or codebase fact.
3. Run `recall` from a later prompt.
4. Use `improve` when the memory needs processing/refinement.

## Agent Connection

Confirm the MCP tool list includes the v1.0 memory tools:

- `remember`
- `recall`
- `forget_memory`
- `improve`

Then test whether the agent naturally calls `recall` during a task.

## Verification

Ask:

```text
Remember that this repo treats unsupported claims as Unknown, not guesses.
```

Then ask:

```text
How should unsupported claims be represented in this repo?
```

Confirm the agent calls Cognee memory and returns the stored rule.

## Known Failure Modes

- Running standalone mode separately in multiple clients and expecting shared memory.
- Connecting to API mode without confirming auth and backend target.
- Legacy tools mixed with v1.0 memory tools.
- Knowledge graph processing not completed before recall testing.

## Sources

- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
