<div align="center">

# Awesome Context Engineering

[![Context Engineering Banner](assets/context-engineering-banner.png)](https://membase.so/?utm_source=github&utm_medium=awesome-context-engineering)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

[![Follow on X](https://img.shields.io/badge/Follow%20on%20X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/mem_base)
[![Follow on LinkedIn](https://img.shields.io/badge/Follow%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/aristotechnologies)
[![Join Discord](https://img.shields.io/badge/Join%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/invite/vRp5Zh3HGu)

</div>

> A living map of AI memory systems, context engineering patterns, and the emerging stack for persistent agent memory.

AI memory is becoming a fragmented stack. ChatGPT remembers you inside ChatGPT. Claude and Gemini have their own personalization layers. Coding agents rely on rules, repo context, local config, and sometimes MCP. Local memory systems build personal brains. Infrastructure products expose memory APIs for developers.

This repo tracks that landscape so builders, researchers, and teams can compare how different systems store, retrieve, control, and share memory.

## What This Repo Is For

- Help our team study AI memory systems with a consistent research template.
- Help people interested in context engineering understand how the memory market is evolving.
- Identify the gap between platform-bound memory and portable memory that can work across agents, tools, and teams.
- Provide a practical index for products, protocols, frameworks, and local systems in the AI memory stack.

## Landscape

| Category | What it covers | Examples |
|---|---|---|
| [Frontier AI Platforms](landscape/frontier-platforms.md) | Platform-native memory and personalization inside major AI apps. | ChatGPT, Claude, Gemini |
| [Coding Agents & Developer Harnesses](landscape/coding-agents.md) | Repo context, rules, instructions, agent sessions, and developer workflows. | Claude Code, Codex, Cursor |
| [Local Agent Harnesses](landscape/local-agent-harnesses.md) | Local-first agent shells, tool runners, and desktop/CLI harnesses. | OpenCode, OpenClaw, Hermes |
| [Personal / Local Memory Systems](landscape/personal-memory-systems.md) | Personal knowledge, second-brain tools, local memory, and agent-maintained memory. | Gbrain, Basic Memory, LLM Wiki |
| [Memory Infrastructure & SDKs](landscape/memory-infrastructure.md) | APIs, SDKs, and frameworks for adding memory to products or agents. | Mem0, Zep, Letta |
| [Protocols & Connectors](landscape/protocols-and-connectors.md) | Context ingestion, tool connection, and data access layers. | MCP, filesystem, Notion, Slack |
| [Team / Enterprise Knowledge Memory](landscape/team-knowledge-memory.md) | Organizational knowledge systems, enterprise search, and shared team context. | Glean, Notion AI, Granola |

## Comparison Axes

Use these common axes when comparing every system:

| Axis | Key question |
|---|---|
| Platform-bound vs portable | Does memory stay inside one app, or can it travel across agents and tools? |
| Individual vs shared | Is memory only for one user, or can it support teams, organizations, or multi-agent workflows? |
| Passive context vs active memory | Is context manually supplied, or does the system learn, update, retrieve, and maintain memory over time? |
| Human-facing vs agent-facing | Is the system mainly for people to read, or for agents to call, search, and update? |
| Transparent vs opaque | Can users inspect and control what is remembered? |
| Local vs cloud | Where does the memory live, and what are the privacy and deployment tradeoffs? |

Each category also has its own comparison axes. Use the common system profile first, then add the relevant category-specific template:

| Category | Category-specific template |
|---|---|
| Universal Memory Layers | [templates/category-universal-memory-layer.md](templates/category-universal-memory-layer.md) |
| Frontier AI Platforms | [templates/category-frontier-platform.md](templates/category-frontier-platform.md) |
| Coding Agents & Developer Harnesses | [templates/category-coding-agent.md](templates/category-coding-agent.md) |
| Local Agent Harnesses | [templates/category-local-agent-harness.md](templates/category-local-agent-harness.md) |
| Personal / Local Memory Systems | [templates/category-personal-memory.md](templates/category-personal-memory.md) |
| Memory Infrastructure & SDKs | [templates/category-memory-infra.md](templates/category-memory-infra.md) |
| Protocols & Connectors | [templates/category-protocol-connector.md](templates/category-protocol-connector.md) |
| Team / Enterprise Knowledge Memory | [templates/category-team-knowledge.md](templates/category-team-knowledge.md) |

## Starter System Profiles

These starter files show the intended structure. They are not complete market research yet.

| System | Category | Status |
|---|---|---|
| [Membase](systems/membase.md) | Universal memory layer | Starter profile |
| [ChatGPT Memory](systems/chatgpt-memory.md) | Frontier AI platform | Research stub |
| [Claude Code](systems/claude-code.md) | Coding agent / developer harness | Research stub |
| [Gbrain](systems/gbrain.md) | Personal / local memory system | Research stub |

## Research Template

Use [templates/system-profile.md](templates/system-profile.md) for every system profile. Then add the category-specific analysis section from the relevant template.

The most important fields are:

- What It Remembers
- Memory Scope
- How Memory Is Written
- How Memory Is Retrieved
- User Control
- Portability
- Relationship to Membase
- Sources

The goal is not to write marketing copy. The goal is to make every system comparable under the same common questions while preserving the details that only matter inside each category.

## The Universal Memory Layer Gap

Most memory systems are useful, but they tend to be bound to one platform, one local setup, one agent runtime, or one product surface. This creates a fragmented experience:

- Platform memory does not travel across tools.
- Local memory often stays tied to one machine or harness.
- Team knowledge systems are usually built for human search, not agent-native memory.
- Connectors bring data into agents, but they do not always provide durable, shared memory.

This gap is where universal memory layers become important.

## Membase

[Membase](https://membase.so/?utm_source=github&utm_medium=awesome-context-engineering) is a shared memory layer for AI agents and teams. It is designed to make memory portable across tools such as Claude, Cursor, ChatGPT, Codex, OpenCode, MCP agents, and other agent workflows.

In this repo, Membase is analyzed as one system in the broader landscape and also as a reference point for the portable, shared memory pattern.

## How To Contribute

1. Pick a system from one of the landscape categories.
2. Copy [templates/system-profile.md](templates/system-profile.md) into `systems/<system-name>.md`.
3. Add the relevant category-specific analysis section from `templates/category-*.md`.
4. Fill the profile with source-backed research.
5. Add the system to the relevant `landscape/*.md` page.
6. Open a PR with sources and a short explanation of why the system matters.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the contribution guidelines.
