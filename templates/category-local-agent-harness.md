# Category-Specific Analysis: Local Agent Harness

Use this section for local-first agent shells, desktop agents, CLI harnesses, and custom local runtimes.

## Local Runtime Model

- Is the harness fully local, cloud-dependent, or hybrid?
- Which model providers can it use?
- Can users swap model providers without changing memory?
- How does it manage local files, command execution, tools, and environment state?

## Memory Backend

- Does the harness include its own memory system?
- Can users configure the memory backend?
- Is memory stored in local files, SQLite, vector databases, cloud services, or external APIs?
- Can multiple local agents share the same memory backend?
- Can memory be backed up, synced, or migrated across machines?

## Configuration Portability

- Where are configs stored?
- Can configs be version-controlled?
- Are tool, prompt, memory, and model configs separated?
- Can the same setup be reproduced on another machine?

## Privacy and Security Boundary

- What data stays local?
- What data is sent to model providers or remote services?
- Are tool permissions explicit?
- Can users audit memory writes and tool calls?

## Local Harness Comparison Axes

| Axis | Key question |
|---|---|
| Local-first level | How much works without a cloud platform? |
| Model agnosticism | Can the harness switch models or providers? |
| Memory backend flexibility | Can memory storage be replaced or shared? |
| Config portability | Can the setup move across machines? |
| Tool execution model | How does it run local tools safely? |
| Privacy boundary | What stays local and what leaves the machine? |
