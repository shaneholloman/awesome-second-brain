# Local vs Cloud

| Solution | Local / self-hosted | Hosted / cloud | Best reason to choose it | Main tradeoff |
|---|---|---|---|---|
| [Membase](../solutions/membase.md) | Not the primary model | Yes | Fast shared memory across agents | Less local infrastructure control. |
| [OpenHuman](../solutions/openhuman.md) | Yes, local memory/runtime state and Markdown vault | Yes, managed services for sign-in, model routing, search proxying, OAuth/integrations | Productized local-first personal AI | Local-first does not mean fully offline by default. |
| [GBrain](../solutions/gbrain.md) | Yes, local PGLite and self-hosted Postgres/Supabase paths | HTTP MCP can be deployed remotely | Maximum control over agent brain operations | You operate sync, embeddings, collectors, and maintenance. |
| [Supermemory](../solutions/supermemory.md) | API/self-hosting details depend on product path | Yes | Cross-tool memory with MCP and connectors | Hosted convenience with platform boundaries. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | Yes through OSS/self-hosted setup | Yes through Mem0 Platform | Developer memory layer with hosted or owned stack | Requires memory scope and governance design. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | Graphiti is open source; Zep is managed | Yes | Temporal graph memory for apps | Product engineering required. |
| [Cognee](../solutions/cognee.md) | Yes, standalone/Docker/local setup | Yes, API mode/shared backend | Knowledge graph memory with MCP | Mode choice affects sharing and isolation. |
| [Khoj](../solutions/khoj.md) | Yes | Yes | Personal AI over files with privacy option | Self-hosting still requires source and model setup. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Yes | Optional sync/services | Human-owned local notes | AI memory requires plugins or custom bridges. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | No | Yes | Native ChatGPT personalization | Platform-bound and not portable. |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | Claude Code runs locally, project knowledge is platform-hosted | Yes | Claude-native project context | Platform-scoped unless external MCP memory is added. |
| [NotebookLM](../solutions/notebooklm.md) | No | Yes | Source-grounded research notebook | Static imported sources and platform-bound workflow. |

## Guidance

Local-first systems are better for ownership, auditability, custom schema work, and long-lived personal archives. Hosted systems are better when setup speed, mobile access, OAuth connectors, and cross-agent sharing matter more than operating the storage layer.
