# Set Up Obsidian / Logseq + AI Bridge

## What You Are Building

A local-first notes vault or graph that remains human-owned, then becomes AI-accessible through a plugin, import path, filesystem tool, or external memory layer.

## Choose This If

- You want local notes as the source of truth.
- You already use Obsidian or Logseq.
- You want inspectable Markdown/org-style files, backlinks, graph views, tags, properties, or blocks.
- You are willing to choose and maintain the AI bridge.

## Avoid This If

- You want one-command cross-agent memory.
- You do not want to manage plugins, local files, sync, or backups.
- You need team-wide access control and audit logs out of the box.

## Prerequisites

- Accounts: none for local vault/graph; optional sync accounts.
- Local runtime: Obsidian or Logseq desktop/mobile apps; plugin runtime depends on bridge.
- API keys: optional for AI plugins or external memory services.
- Storage: local files or app database, plus backups/sync if desired.
- Agent clients: plugin, filesystem-aware agent, MCP bridge, or external memory layer such as Membase, GBrain, or Khoj.

## Setup Time

Hands-on: 30-90 minutes for a useful AI bridge after the notes app is installed.

## Install / Connect

1. Create or choose a vault/graph.
2. Establish conventions for folders, links, tags, properties, or blocks.
3. Choose one bridge:
   - import vault into a memory layer such as Membase Wiki, GBrain, or Khoj
   - install an AI/RAG/community plugin
   - expose files through a local MCP/filesystem bridge
   - write a custom collector that summarizes changes into memory
4. Start with read-only retrieval before allowing AI write-back.

## Data-Source Setup

Capture normal human notes first:

- daily notes
- meeting notes
- project docs
- people/company notes
- decisions
- source links
- PDFs or annotations where supported

Use frontmatter/properties/tags to make later AI extraction safer.

## Agent Connection

For read-only access, let the agent search or retrieve notes. For write-back, require review:

```text
agent proposes note edit -> user reviews diff -> write to vault -> index/update external memory
```

## Verification

1. Add a note with a unique phrase and a link to another note.
2. Ask the agent a question requiring that phrase.
3. Ask a follow-up requiring the linked note.
4. Confirm the bridge retrieves both without hallucinating unrelated vault content.

## Known Failure Modes

- AI plugin has too much filesystem access.
- Agent writes low-quality notes directly into the vault.
- Sync conflicts create duplicate or stale notes.
- Graph view looks connected but agent retrieval still misses the right note.
- External memory import treats raw imported notes as curated knowledge.

## Sources

- [Obsidian core plugins](https://obsidian.md/help/plugins)
- [Obsidian graph view](https://obsidian.md/help/Plugins/Graph%2Bview)
- [Logseq](https://logseq.com/)
