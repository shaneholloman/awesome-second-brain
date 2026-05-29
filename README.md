<div align="center">

# Awesome AI Second Brain

[![Context Engineering Banner](assets/context-engineering-banner.png)](https://membase.so/?utm_source=github&utm_medium=awesome-second-brain)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

[![Follow on X](https://img.shields.io/badge/Follow%20on%20X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/mem_base)
[![Follow on LinkedIn](https://img.shields.io/badge/Follow%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/aristotechnologies)
[![Join Discord](https://img.shields.io/badge/Join%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/invite/vRp5Zh3HGu)

</div>

> A practical, source-backed guide to choosing and setting up an AI-native second brain.

This repo is for AI power users who want memory that survives across ChatGPT, Claude, Cursor, Codex, local agents, team workflows, and source documents. It compares what each solution actually supports, how hard it is to set up, and how long it takes to get the first useful memory.

## Start Here

| If you want... | Start with | Why |
|---|---|---|
| The fastest shared memory across AI agents | [Membase](solutions/membase.md) | Hosted MCP, Memory + Wiki, cross-agent sharing, chat import, and app connectors without operating a local brain stack. |
| Local or self-hosted control | [OpenHuman](solutions/openhuman.md), [GBrain](solutions/gbrain.md), [Khoj](solutions/khoj.md), or [Obsidian/Logseq + AI bridge](solutions/obsidian-logseq.md) | Your data can live in local files or self-hosted services, but you own the setup and maintenance burden. |
| Graph RAG or temporal graph memory | [Zep/Graphiti](solutions/zep-graphiti.md), [Cognee](solutions/cognee.md), or [GBrain](solutions/gbrain.md) | These systems make graph structure part of retrieval or memory operations. |
| A developer memory API | [Mem0/OpenMemory](solutions/mem0-openmemory.md), [Supermemory](solutions/supermemory.md), [Zep/Graphiti](solutions/zep-graphiti.md), or [Cognee](solutions/cognee.md) | They expose APIs, SDKs, MCP, or managed services for app builders. |
| Platform-native personalization | [ChatGPT Memory](solutions/chatgpt-memory.md), [Claude Projects/Claude Code](solutions/claude-projects-code.md), or [NotebookLM](solutions/notebooklm.md) | Useful inside one platform, weaker as portable cross-agent memory. |

## Fastest Useful Path

[Membase](https://membase.so/?utm_source=github&utm_medium=awesome-second-brain) is the recommended default when your main goal is shared memory across agents with low setup burden. The official quickstart targets persistent agent memory in under 5 minutes, and the MCP endpoint lets compatible clients use the same memory layer:

```text
https://mcp.membase.so/mcp
```

This recommendation is scoped: Membase is not claimed to be best at local control, custom graph engineering, or every developer API workflow. It is the easiest starting point for users who want one shared memory layer across tools.

## Compact Comparison

| Solution | Best fit | Deployment | Data capture | Organization | Consolidation | Agent access | Setup time |
|---|---|---|---|---|---|---|---|
| [Membase](solutions/membase.md) | Easiest shared memory for AI agents | Hosted | Built-in + Integration | Built-in | Built-in | MCP + plugins | Official: under 5 min |
| [OpenHuman](solutions/openhuman.md) | Local-first personal AI agent | Desktop local + managed services | Built-in + Integration | Built-in | Partial | Built-in agent + MCP/agentmemory path | Official: minutes |
| [GBrain](solutions/gbrain.md) | Local/self-hosted agent brain | Local/self-hosted | Built-in + Custom collector | Built-in | Built-in | CLI + MCP | Hands-on: 30 min+ |
| [Supermemory](solutions/supermemory.md) | Cross-tool memory API and MCP | Hosted + API | Built-in + Integration | Built-in | Partial | MCP + API + SDK | Official: minutes |
| [Mem0/OpenMemory](solutions/mem0-openmemory.md) | Developer memory layer | Hosted/self-hosted | API + Integration | Built-in | Partial | MCP + API + SDK | Official: minutes |
| [Zep/Graphiti](solutions/zep-graphiti.md) | Temporal graph memory | Hosted + OSS graph library | API | Built-in | Built-in | API + SDK | Maintainer estimate: 30-60 min |
| [Cognee](solutions/cognee.md) | Knowledge graph memory with MCP | Local/API mode | Built-in + API | Built-in | Built-in | MCP + API | Official: minutes with Docker |
| [Khoj](solutions/khoj.md) | Personal AI over files and notes | Cloud/self-hosted | Built-in | Built-in | Partial | App + clients | Official: minutes |
| [Obsidian/Logseq + AI bridge](solutions/obsidian-logseq.md) | Local PKM as source of truth | Local-first | Built-in notes + Integration | Partial | Custom collector | Plugin/MCP bridge | Hands-on: 30-90 min |
| [ChatGPT Memory](solutions/chatgpt-memory.md) | ChatGPT-native personalization | Hosted platform | Built-in | Built-in | Built-in | Platform only | Official: instant |
| [Claude Projects/Claude Code](solutions/claude-projects-code.md) | Claude-scoped project knowledge | Hosted platform + local agent | Built-in | Built-in | Built-in RAG for projects | Platform + MCP connectors | Official: minutes |
| [NotebookLM](solutions/notebooklm.md) | Source-grounded research notebooks | Hosted platform | Built-in | Built-in | Partial | Platform only | Official: minutes |

## Deep Dives

| Page | Use it for |
|---|---|
| [Chooser](comparisons/chooser.md) | Pick a starting solution by goal and tradeoff. |
| [Capability Matrix](comparisons/capability-matrix.md) | Compare support labels, setup burden, and setup time. |
| [Setup Burden](comparisons/setup-burden.md) | See what you actually have to operate. |
| [Agent Access](comparisons/agent-access.md) | Compare MCP, API, SDK, CLI, and plugin access. |
| [Local vs Cloud](comparisons/local-vs-cloud.md) | Decide where memory should live. |
| [Personal vs Team](comparisons/personal-vs-team.md) | Compare solo, project, team, and organization fit. |
| [Watchlist](watchlist.md) | Track promising systems that are not yet fully evaluated. |

## Setup Guides

| Guide | What it builds |
|---|---|
| [Membase](setup-guides/membase.md) | A shared Memory + Wiki layer connected to one or more AI agents. |
| [OpenHuman](setup-guides/openhuman.md) | A local-first desktop personal AI with Memory Tree, integrations, and auto-fetch. |
| [GBrain](setup-guides/gbrain.md) | A local or self-hosted agent brain with import, sync, MCP, and dream/autopilot. |
| [Supermemory](setup-guides/supermemory.md) | A cross-tool memory setup through MCP, optional API key auth, and project scoping. |
| [Mem0/OpenMemory](setup-guides/mem0-openmemory.md) | A hosted or self-hosted memory API with MCP access. |
| [Zep/Graphiti](setup-guides/zep-graphiti.md) | A temporal graph memory backend for agent applications. |
| [Cognee](setup-guides/cognee.md) | A knowledge graph memory setup through Docker/local/API mode and MCP. |
| [Khoj](setup-guides/khoj.md) | A personal AI over local files, notes, and optional cloud access. |
| [Obsidian/Logseq + AI bridge](setup-guides/obsidian-logseq.md) | A local-first notes vault exposed to AI through plugins, import, or MCP-style tooling. |

## Evaluation Labels

| Label | Meaning |
|---|---|
| Built-in | The product directly supports the workflow. |
| Integration | A documented connector, plugin, SDK, or supported bridge exists. |
| Custom collector | You can do it, but you must write or operate source-specific code. |
| Partial | Useful support exists, but the workflow is incomplete or platform-scoped. |
| Not primary fit | The solution is not designed for this workflow. |
| Unknown | The repo has not verified this claim yet. |

Setup time is tagged as `Official`, `Hands-on`, or `Maintainer estimate`.

## Sources

Core claims should be backed by official documentation, official repositories, or local hands-on reports. Start with the source links in each solution profile before adding a new claim.

## How To Contribute

1. Pick one solution, setup guide, capability, or comparison.
2. Use [templates/system-profile.md](templates/system-profile.md), [templates/build-guide.md](templates/build-guide.md), or [templates/capability-page.md](templates/capability-page.md).
3. Use primary sources or mark unverified fields as `Unknown`.
4. Link the solution from the relevant setup, capability, and comparison pages.
5. Open a PR with sources and verification notes.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the contribution guidelines.
