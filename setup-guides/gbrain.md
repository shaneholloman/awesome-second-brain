# Set Up GBrain

## What You Are Building

This guide builds a local or self-hosted AI second brain with GBrain. The core workflow is:

```text
source data -> deterministic collector or Markdown import -> brain pages -> chunks, links, timeline, facts -> search/query/think -> agent reads and writes through CLI or MCP -> dream/autopilot keeps the brain maintained
```

GBrain is strongest when you want an agent-operable brain rather than a passive notes archive. It gives you storage, indexing, retrieval, graph/timeline extraction, and maintenance loops. For external active context, such as Gmail, Calendar, Slack, or Notion, you still need source-specific collectors or exports that turn raw data into pages.

## Choose This If

- You want a local or self-hosted second brain.
- You are comfortable with Markdown, git, CLI tools, scheduled jobs, and agent setup.
- You want other agents to read/write through MCP or CLI.
- You want a periodic maintenance loop, not just search.
- You can tolerate custom collector work for active context sources.

## Avoid This If

- You want a fully managed no-code app with every connector already wired.
- You do not want to operate sync, embed, dream, upgrade, or collector jobs.
- Your highest priority is a polished human-facing notes UI.
- You need turnkey Slack/Gmail/Notion sync without custom setup.

## Requirements

- Accounts: none for local PGLite; provider accounts for embeddings, LLM expansion, external data sources, or remote hosting.
- Local runtime: Bun and the `gbrain` CLI.
- Storage: PGLite by default; Postgres/Supabase for team, remote, or larger deployments.
- API keys: embedding provider for vector/hybrid search; LLM keys for expansion and synthesis features.
- Agent clients: optional, but useful. Claude Code, Cursor, Hermes, OpenClaw, ChatGPT connector, and other MCP clients can be wired through stdio or HTTP MCP depending on client support.

## Setup Time

Hands-on: 30 minutes or more for a useful local brain. External active-context sources add source-specific collector work.

## Setup Path

### 1. Install and initialize

```bash
bun install -g github:garrytan/gbrain
gbrain --version
gbrain init --pglite
gbrain doctor --json
```

If a global install fails, GBrain's install guide recommends a clone plus `bun link` fallback.

### 2. Create or choose a brain repo

```bash
mkdir -p ~/brain
cd ~/brain
git init
```

Your brain repo is separate from the GBrain tool repo. It holds the Markdown pages your agents read and write.

### 3. Import existing notes or exports

```bash
gbrain import ~/brain --no-embed
gbrain extract links --source db --dry-run | head -20
gbrain extract links --source db
gbrain extract timeline --source db
gbrain embed --stale
gbrain stats
```

For Obsidian-style Markdown, wikilinks and folder conventions are a good fit. For Notion exports, expect cleanup. Local testing imported 327 Markdown files from a Notion export into searchable pages, but CSV properties, UUID filenames, and Notion relation graph cleanup were not automatic.

Treat import as a staged quality pipeline:

| State | What it means | Product implication |
|---|---|---|
| Imported | Page and chunks exist; keyword search can work immediately. | Do not present this as "curated wiki complete." |
| Embedded | Vector/hybrid retrieval can improve after embeddings are present. | Track stale chunks, missing embeddings, and retry reasons. |
| Curated | Schema, links, facts, timeline, and review state are good enough for agent use. | Prefer proposal/preview/approve flows for risky changes. |

### 4. Keep Markdown sources current

Always chain sync and embed:

```bash
gbrain sync --repo /path/to/brain && gbrain embed --stale
```

Recommended operating paths:

| Path | Use when |
|---|---|
| Cron every 5-30 minutes | You want reliable background sync. |
| `gbrain sync --watch --repo /path/to/brain` | You want near-real-time polling and have a process manager. |
| Git hook or webhook | You want push-triggered sync and can operate the server path. |

For source status, track more than whether the connector exists:

| Surface | Status to expose |
|---|---|
| Sync | Last successful run, last error, changed files, skipped files, failed files, delete/rename handling. |
| Index | Chunks created, stale chunks, embedded count, missing embedding reason, retry queue. |
| Review | Unknown type, orphan pages, unresolved references, candidate schema suggestions. |

## Data Capture Workflow

| Source | Built-in support | Setup path | Notes |
|---|---|---|---|
| Manual thoughts | Yes | `gbrain capture`, stdin, file capture, inbox folder | Good first path for personal memory. |
| Markdown / Obsidian | Yes | `gbrain import`, `gbrain sync`, `extract links`, `embed --stale` | Wikilinks and folder structure help graph quality. |
| Notion export | Partial | Export to Markdown, import, then clean slugs/properties/links | Search works; graph/property mapping needs extra work. |
| Gmail | Recipe plus collector work | `credential-gateway` and `email-to-brain` style workflow | Local report confirmed 684 messages through a custom collector. |
| Calendar | Recipe plus collector work | `credential-gateway` and `calendar-to-brain` style workflow | Local report confirmed 25 events through a custom collector. |
| Slack | Custom collector likely required | Direct Slack token or gateway path | Local report hit shared gateway rate limits; direct-token collector was drafted but not run. |
| Meetings | Recipe available | `meeting-sync` style workflow | Transcript provider and attendee matching remain setup work. |
| Webhooks | Yes | POST Markdown to ingestion endpoint | Useful for Shortcuts, Zapier, and custom events. |

Recommended ingestion pattern:

```text
raw source event -> deterministic collector -> JSON/digest -> agent judgment -> page or timeline update -> GBrain indexes and links it
```

This matters because the mechanical parts, such as pagination, links, timestamps, and rate limits, should be handled by code. The agent should handle judgment: which entities matter, what belongs in compiled truth, what should become a durable timeline event, and what should stay raw.

## Organization Workflow

Use GBrain's structure after data lands:

```bash
gbrain schema active
gbrain schema detect
gbrain schema suggest
gbrain schema review-candidates
gbrain extract links --source db
gbrain extract timeline --source db
```

The useful model is not "everything auto-sorts perfectly." It is:

```text
imported pages -> type/schema inference -> links/timeline/facts -> review or repair -> search-ready brain
```

For new local trusted writes, `put_page` can run write-time auto-link reconciliation. For historical imports, run extraction/backfill commands.

Page type inference is rule-driven:

| Priority | Signal | Setup implication |
|---|---|---|
| 1 | Frontmatter `type` | Collectors should write explicit types when source meaning is known. |
| 2 | Active schema pack path prefixes | Design paths such as `people/`, `companies/`, `meetings/`, or team-specific prefixes before bulk import. |
| 3 | Built-in fallback / catch-all | Unmatched content can fall back to generic types and may need review. |
| 4 | Subtype rules | Use frontmatter fields or schema rules when a broad type needs finer workflow categories. |

GBrain's graph behavior is deterministic-first. Wikilinks, Markdown links, slug references, and frontmatter relations can become graph edges. Plain-text entity mentions can be matched with a gazetteer-style pass. Semantic similarity alone should be treated as a candidate relationship, not a confirmed edge.

## Dreaming / Consolidation Workflow

GBrain's dream cycle is the periodic maintenance loop. Use it for already-ingested data:

```bash
gbrain dream
gbrain autopilot --install
```

Common recurring jobs:

```bash
# every 5-30 minutes
gbrain sync --repo /path/to/brain && gbrain embed --stale

# nightly
gbrain dream

# weekly
gbrain doctor --json && gbrain embed --stale
```

The local evaluation report describes the dream/autopilot cycle as maintenance over the brain: sync, extract, facts, patterns, consolidation, embeddings, orphan checks, schema suggestions, and cleanup. It is not a replacement for Gmail, Slack, Calendar, or Notion API polling.

## Agent Access Workflow

### Local stdio MCP

Use this for local MCP-aware clients:

```bash
gbrain serve
```

MCP config shape:

```json
{
  "command": "gbrain",
  "args": ["serve"]
}
```

### HTTP MCP

Use this for remote clients and OAuth-scoped access:

```bash
gbrain serve --http --port 3131 --bind 0.0.0.0 --public-url https://brain.example.com
```

Important verification rule: installed MCP tools are not the same as actual agent usage. Check runtime logs or ask the host agent a brain-dependent question and confirm a `search`, `query`, or `get_page` call occurred.

Local Hermes testing confirmed that GBrain MCP worked once the `gbrain` command resolved correctly. The test observed stats and page reads through MCP. General autonomous search/query behavior still needs workflow-specific verification.

The architecture exposes a shared operation contract through CLI and MCP. Local CLI callers and remote MCP callers do not always have the same trust level. Verify mutating operations, provenance writes, file operations, and auto-link behavior through the actual client path you plan to use.

## Team / Workspace Workflow

For team use, move beyond local PGLite:

```bash
gbrain migrate --to supabase
gbrain sources add shared --path /srv/brain-repos/shared --name "Shared company wiki"
gbrain sources add customers --path /srv/brain-repos/customers --name "Customer notes"
gbrain sources add internal --path /srv/brain-repos/internal --name "Internal-only"
gbrain sync --all
gbrain serve --http --port 3131 --bind 0.0.0.0 --public-url https://brain.example.com
```

Then register scoped clients:

```bash
gbrain auth register-client alice \
  --grant-types client_credentials \
  --scopes read,write \
  --source customers \
  --federated-read customers,shared
```

The company-brain pattern uses sources, OAuth clients, and federated read scopes to separate users, teams, and sensitive source categories.

Use the brain/source distinction when designing team setups:

- Brain: database boundary, such as local PGLite, Postgres, or a mounted team brain.
- Source: content boundary inside a brain, such as a shared wiki repo, Notion export, Gmail account, Slack channel, customer notebook, or internal docs repo.
- Operation: the shared read/write/admin contract exposed by CLI and MCP.

## Verification

Run checks at each layer:

```bash
gbrain doctor --json
gbrain stats
gbrain search "known phrase from an imported page"
gbrain query "known topic from the brain"
gbrain extract links --source db --dry-run | head -20
gbrain embed --stale --dry-run --json
```

For agent access:

1. Ask the agent for a known page or phrase.
2. Confirm the agent called GBrain MCP or CLI.
3. Confirm the answer includes the expected title, phrase, slug, or citation.
4. Repeat without explicitly saying "use GBrain" to test natural adoption.

## Known Gaps

- Notion import needs cleanup for UUID filenames, database properties, relation mapping, and graph reconstruction.
- Slack ingestion needs careful token and rate-limit handling.
- Active context needs a raw -> digest -> candidate fact/timeline -> approved page workflow to avoid noisy durable memory.
- Remote MCP write trust boundaries can affect auto-link behavior.
- Agent adoption depends on skills, resolver rules, and host runtime behavior.
- Graph edges are not semantic guesses by default; relation quality depends on explicit links, frontmatter, schema rules, or reviewed candidate edges.

## Sources

- [GBrain GitHub repo](https://github.com/garrytan/gbrain)
- [GBrain installation guide for AI agents](https://github.com/garrytan/gbrain/blob/master/INSTALL_FOR_AGENTS.md)
- [GBrain integrations docs](https://github.com/garrytan/gbrain/blob/master/docs/integrations/README.md)
- [GBrain live sync guide](https://github.com/garrytan/gbrain/blob/master/docs/guides/live-sync.md)
- [GBrain company brain tutorial](https://github.com/garrytan/gbrain/blob/master/docs/tutorials/company-brain.md)
- Internal dogfooding report: `2026-05-27-gbrain-gmail-calendar-slack-setup-report.md`
- Internal evaluation report: `2026-05-28-gbrain-hermes-knowledge-automation-report.md`
- Internal Wiki analysis deck: `2026-05-28-gbrain-wiki-analysis-deck.html`
