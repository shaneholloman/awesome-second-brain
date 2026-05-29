# Membase

## Snapshot

- Website / docs: https://membase.so/ and https://docs.membase.so/
- Company / maintainer: Aristo Technologies
- Status: Active hosted product
- Open source: Hosted service with public MCP/plugin setup paths
- Deployment: Cloud-hosted shared memory layer
- Primary users: AI power users, agent users, and teams using multiple AI tools
- Best second-brain role: Easiest shared memory layer across agents
- Last reviewed: 2026-05-29

## One-line Summary

Membase is a hosted universal knowledge layer with two shared stores: Memory for personal context and Knowledge Wiki for factual reference material.

## Second-Brain Fit

Membase is the best default when the user wants useful memory quickly across ChatGPT, Claude, Claude Code, Codex, Cursor, VS Code, OpenCode, OpenClaw, Hermes, and other MCP-compatible tools. It is not the most local-control-oriented choice; it optimizes for low setup burden, cross-agent sharing, and external context import.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment | Hosted cloud service with remote MCP endpoint at `https://mcp.membase.so/mcp`. |
| Data capture | Built-in agent memory writes, chat history import, Gmail/Calendar/Slack connectors, and Obsidian vault import paths are documented. |
| Auto-organization | Built-in. Memories are digested into structured personal context and a knowledge graph; Wiki stores linked markdown documents in collections. |
| Consolidation / dreaming | Built-in. Product docs describe smart digesting and automatically updated shared memory, but detailed scheduling internals are product-managed. |
| Retrieval model | `search_memory` for personal context and `search_wiki` for factual knowledge; Wiki search is described as hybrid. |
| Agent access | Built-in MCP plus plugin/setup paths for Claude Code, OpenClaw, Hermes, Codex, Cursor, VS Code, OpenCode, ChatGPT, Claude, Gemini CLI, and generic MCP clients. |
| Workspace / team support | Strong fit for shared memory; exact workspace governance should be verified against current product settings for the target team. |
| UI / filtering | Dashboard, Chat with Memory, Memory, Wiki, profile/recent resources, and app/agent setup surfaces. |
| Privacy / control | Hosted model. Users should verify export, deletion, and retention requirements against current docs and product settings. |
| Setup burden | Low. Official quickstart targets persistent agent memory in under 5 minutes. |

## Strengths

- Fastest path from "my agents forget me" to shared persistent memory.
- Clear Memory vs Wiki split.
- Cross-agent sharing is the primary product model.
- MCP endpoint and supported client installers reduce setup friction.
- Good positioning for users who do not want to run a local graph, vector DB, cron jobs, or collectors.

## Limitations

- Not local-first or self-hosted by default.
- Deep customization of graph construction and indexing is less exposed than in local/self-hosted systems.
- Team governance, export, and retention requirements should be checked for the target use case.

## Best For

- AI power users who use more than one agent.
- Teams that want shared context without operating memory infrastructure.
- Users who want external app context and chat history to feed one agent-accessible layer.

## Not Ideal For

- Users who require local-only storage.
- Builders who need to customize every retrieval, graph, and embedding component.
- Research workflows that primarily need static source analysis rather than ongoing personal memory.

## Relationship to Membase

This is the reference profile. Keep it factual: Membase should be recommended as the easiest shared-memory default, not as the winner for every dimension.

## Setup Guide

- [Set up Membase](../setup-guides/membase.md)

## Sources

- [Membase overview](https://docs.membase.so/)
- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Attached vs Universal memory](https://docs.membase.so/core-concepts/attached-vs-universal)
- [Membase MCP](https://docs.membase.so/features/membase-mcp)
