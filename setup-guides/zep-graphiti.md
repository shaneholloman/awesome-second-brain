# Set Up Zep / Graphiti

## What You Are Building

A temporal knowledge graph memory backend for an agent application. The core workflow is:

```text
chat or business data -> Zep graph episodes -> entities, facts, summaries -> graph search / Graph RAG -> agent context
```

## Choose This If

- You are building an application, not just configuring a personal agent.
- You need temporal memory, entity relationships, facts, summaries, and business data.
- Graph RAG is a core requirement.

## Avoid This If

- You want one-command personal memory across daily AI tools.
- You need a local Markdown brain as the source of truth.
- You do not want to model users, sessions, groups, or ingestion flows.

## Prerequisites

- Accounts: Zep account for hosted platform.
- Local runtime: application runtime for SDK/API integration.
- API keys: Zep API credentials.
- Storage: hosted Zep or Graphiti-backed stack depending on path.
- Agent clients: your application or agent framework.

## Setup Time

Maintainer estimate: 30-60 minutes for a first integrated proof of concept; production memory design takes longer.

## Install / Connect

1. Create a Zep project.
2. Model users, sessions, and groups.
3. Add chat history or business data through Zep ingestion APIs.
4. Query relevant facts or graph context from the agent runtime.

For Graphiti-specific experiments, start from the Graphiti docs and build a minimal graph ingestion/query loop before wiring it to an agent.

## Data-Source Setup

Send data as:

- chat episodes
- business data
- structured JSON or unstructured text through graph endpoints

Track where each fact came from. Temporal memory is only useful if source time, validity, and update behavior are clear.

## Agent Connection

Most agent access is through API/SDK integration inside your app. The agent should retrieve relevant facts/summaries before responding and write new conversation/business data back after important events.

## Verification

1. Add a user preference.
2. Add a later conflicting or updated preference.
3. Ask a question that requires the latest valid fact.
4. Confirm the graph result reflects time-aware memory rather than a stale flat vector hit.

## Known Failure Modes

- Treating temporal graph memory as simple document RAG.
- Not modeling users, sessions, groups, or business-data boundaries.
- Ingesting raw events without timestamps or provenance.
- Expecting end-user no-code setup from a developer memory backend.

## Sources

- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Zep memory docs](https://help.getzep.com/v2/memory)
- [Graphiti open source](https://www.getzep.com/product/open-source)
- [Graphiti GitHub repo](https://github.com/getzep/graphiti)
