# Category-Specific Analysis: Memory Infrastructure / SDK

Use this section for developer-facing memory APIs, SDKs, frameworks, hosted services, and self-hosted memory infrastructure.

## Developer Primitives

- What primitives does the system expose: memories, facts, events, sessions, users, entities, documents, graphs?
- Are write, search, update, delete, and export APIs available?
- Does it provide SDKs for common languages and agent frameworks?
- Can developers inspect why a memory was retrieved?

## Memory Lifecycle

- How are memories extracted?
- How are memories ranked, merged, updated, expired, or deleted?
- Is there a notion of confidence, recency, importance, or decay?
- Can users or developers correct bad memories?
- Are memory changes versioned or auditable?

## Production Readiness

- Does it support multi-user, multi-tenant, team, or organization scopes?
- How does permissioning work?
- What deployment options exist: hosted, self-hosted, embedded, hybrid?
- What observability, evals, logs, or debugging tools exist?
- How does it handle privacy and compliance requirements?

## Integration Surface

- Which agent frameworks, model providers, and tool protocols are supported?
- Can it be used outside a single application?
- Does it support MCP or agent-native tool calls?
- How hard is it to replace or migrate away from the infrastructure?

## Memory Infrastructure Comparison Axes

| Axis | Key question |
|---|---|
| API completeness | Are full memory lifecycle APIs available? |
| Extraction quality | How are useful memories created from raw interactions? |
| Retrieval control | Can developers tune and debug retrieval? |
| Multi-user support | Does it support real product/team scopes? |
| Deployment flexibility | Hosted, self-hosted, embedded, or hybrid? |
| Framework portability | Can it work across multiple agent stacks? |
