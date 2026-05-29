# Set Up Khoj

## What You Are Building

A personal AI that can chat with and search your files, notes, documents, and selected sources through Khoj Cloud or a self-hosted instance.

## Choose This If

- You want an open-source personal AI over your files and notes.
- You use Markdown, org-mode, PDFs, plaintext, Notion pages, Obsidian, or Emacs.
- You want cloud convenience or self-hosted privacy.

## Avoid This If

- You need universal memory across many unrelated AI agents.
- You need agent write-back and shared team memory as the core workflow.
- You want temporal graph memory or a developer memory API.

## Prerequisites

- Accounts: Khoj Cloud account for hosted setup; none or provider accounts for self-hosting depending on model choices.
- Local runtime: self-host requirements from Khoj docs if running privately.
- API keys: model/provider keys as required by the chosen deployment.
- Storage: Khoj Cloud or self-hosted instance.
- Clients: web browser, desktop app, Obsidian, Emacs, or other supported clients.

## Setup Time

Official: minutes for cloud quickstart. Self-hosting is medium effort.

## Install / Connect

1. Try Khoj Cloud for the fastest path, or follow the self-host docs.
2. Add initial sources: Markdown, PDF, plaintext, org-mode, or Notion pages.
3. Connect your preferred client, such as Obsidian, Emacs, desktop, or browser.
4. Ask a question that requires one of the indexed sources.

## Data-Source Setup

Use sources that match Khoj's strengths:

- PDFs
- plaintext
- Markdown
- org-mode files
- Notion pages
- notes exposed through Obsidian or Emacs

For ongoing memory, keep source folders organized and verify re-indexing behavior.

## Agent Connection

Khoj is primarily a personal AI/client experience. If you need other agents to use the same memory, verify the current API, client, or bridge path before treating it as portable memory.

## Verification

Add a small Markdown file with a unique phrase, then ask:

```text
What does my note say about the project launch constraint?
```

Confirm Khoj retrieves the note and cites or references the expected content.

## Known Failure Modes

- Source folder is not indexed or re-indexed.
- Cloud and self-hosted instances point at different data.
- Treating Khoj as universal shared agent memory when the workflow is actually personal assistant Q&A.
- Large or messy source sets reduce answer quality without organization.

## Sources

- [Khoj docs](https://docs.khoj.dev/)
