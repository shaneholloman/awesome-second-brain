# Set Up OpenHuman

## What You Are Building

A local-first desktop personal AI agent with persistent memory, a local Memory Tree, an Obsidian-style Markdown vault, semantic search, voice/UI features, and app integrations that can auto-fetch fresh context.

## Choose This If

- You want a full desktop AI assistant, not just a memory API.
- You want local memory files and a UI-first setup.
- You want automatic app data capture through many third-party integrations.
- You are comfortable trying early beta software.

## Avoid This If

- You need mature team/workspace governance.
- You want one shared memory layer across many independent agents.
- You need a stable production backend API more than a personal desktop agent.
- You require a fully offline default experience with no managed services.

## Prerequisites

- Accounts: OpenHuman account for the managed default experience.
- Local runtime: macOS, Windows, or Linux desktop environment.
- API keys: optional if bringing custom/local model, search, or connector credentials.
- Storage: local OpenHuman memory/runtime state and Markdown vault.
- Agent clients: OpenHuman desktop app first; related persistent storage sharing may use agentmemory/MCP workflows.

## Setup Time

Official: minutes for native package install and first run. Hands-on setup grows with connected apps and custom provider choices.

## Install / Connect

Recommended macOS path:

```bash
brew tap tinyhumansai/core
brew install openhuman
```

Debian/Ubuntu path:

```bash
sudo apt-get install -y --no-install-recommends gnupg2 curl ca-certificates
curl -fsSL https://tinyhumansai.github.io/openhuman/apt/KEY.gpg \
  | sudo gpg --dearmor -o /etc/apt/keyrings/openhuman.gpg
echo "deb [signed-by=/etc/apt/keyrings/openhuman.gpg arch=amd64] \
  https://tinyhumansai.github.io/openhuman/apt stable main" \
  | sudo tee /etc/apt/sources.list.d/openhuman.list
sudo apt-get update
sudo apt-get install -y openhuman
```

Windows and direct installer paths are available from the project releases and OpenHuman site.

## Data-Source Setup

Start with the app's onboarding, then connect a small number of high-value sources first:

- Gmail
- Calendar
- Slack
- Notion
- GitHub
- Drive

The docs describe 118+ third-party integrations and an auto-fetch loop that pulls fresh data into the Memory Tree every 20 minutes. Verify each connector's OAuth scope and sync status before relying on it.

## Agent Connection

OpenHuman is primarily its own agent experience. Use the built-in assistant, UI, and memory surfaces first. If you need to share memory with Claude Code, Cursor, Codex, OpenCode, or other tools, evaluate the documented agentmemory/MCP backend path separately and confirm the same persistent storage is actually being used.

## Verification

1. Install and open the app.
2. Add a durable preference or fact through the assistant.
3. Connect one source, such as Calendar or GitHub.
4. Wait for or trigger sync.
5. Ask a question that requires both the remembered preference and the connected source.
6. Confirm the answer cites or clearly uses the expected local memory/source state.

## Known Failure Modes

- Treating local-first as fully offline; default managed services still handle sign-in, model routing, search proxying, and managed OAuth/integration flows.
- Connecting too many integrations before verifying one source works.
- Assuming auto-fetch means curated knowledge quality.
- Expecting team/workspace memory governance from a personal-first desktop agent.
- Beta releases may change setup paths and memory behavior quickly.

## Sources

- [OpenHuman GitHub repo](https://github.com/tinyhumansai/openhuman)
- [OpenHuman Wiki](https://openhumanwiki.com/)
- [OpenHuman user guide](https://www.openhuman.dev/)
