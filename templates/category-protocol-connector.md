# Category-Specific Analysis: Protocol / Connector

Use this section for protocols, connectors, and tool integrations that expose context or actions to agents.

## Context Access Model

- What data sources does it expose?
- Is access read-only, write-only, or read-write?
- Does it expose raw data, structured objects, search results, or actions?
- Does it store durable memory, or only provide access to external context?

## Authentication and Permissions

- How does authentication work?
- Are permissions scoped per user, workspace, app, source, or tool?
- Can users see and revoke access?
- Are writes auditable?

## Memory Layer Compatibility

- Can outputs from this connector be written into a memory layer?
- Can the connector read from a memory layer?
- Does it support MCP, API calls, webhooks, or another integration pattern?
- Is it easy to compose with agents and memory infrastructure?

## Operational Constraints

- Is it local, remote, hosted, or self-hosted?
- What rate limits, data limits, or permission limits apply?
- How does it handle sync, freshness, and source-of-truth conflicts?
- What failure modes matter for agents?

## Protocol / Connector Comparison Axes

| Axis | Key question |
|---|---|
| Storage vs access | Does it store memory or only expose context? |
| Read/write capability | Can agents write back to the source system? |
| Permission model | Is access scoped and auditable? |
| Composability | Can it plug into agents and memory layers cleanly? |
| Freshness | How current is the exposed context? |
| Source-of-truth risk | Can memory diverge from the original data source? |
