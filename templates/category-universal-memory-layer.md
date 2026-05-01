# Category-Specific Analysis: Universal Memory Layer

Use this section for systems designed to make memory portable across multiple agents, tools, users, teams, or applications.

## Portability Model

- Which agents, apps, or tools can read and write the memory?
- Is memory portable through an API, MCP server, SDK, connector, sync layer, or export?
- Can the same memory be reused across frontier platforms, coding agents, local harnesses, and team workflows?
- What parts of memory remain system-specific?

## Shared Memory Model

- Does memory support individual, project, team, and organization scopes?
- Can multiple agents write to the same memory space?
- Are there permissions, ownership, or collaboration controls?
- How are conflicts between users, agents, and sources resolved?

## Memory Object Model

- What are the core objects: memories, facts, wiki pages, entities, events, documents, summaries, relationships?
- Does the system distinguish raw context from curated memory?
- Are memories structured, searchable, versioned, or linked?
- How does it handle stale, duplicate, or contradictory memory?

## Integration and Retrieval Surface

- Which tool protocols and app integrations are supported?
- Can memory be retrieved through search, tool calls, prompt injection, API, or graph traversal?
- Can developers build directly on top of the memory layer?
- Can non-technical users inspect and manage memory?

## Universal Memory Layer Comparison Axes

| Axis | Key question |
|---|---|
| Cross-agent portability | Can memory move across multiple agent surfaces? |
| Shared scope | Does memory support users, projects, teams, and organizations? |
| Write interoperability | Can multiple agents and apps safely write memory? |
| Retrieval interoperability | Can multiple agents and apps retrieve the same memory? |
| Memory governance | Are permissions, conflicts, edits, and deletion handled clearly? |
| Developer surface | Is there a clean API, SDK, MCP server, or tool interface? |
