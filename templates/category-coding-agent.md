# Category-Specific Analysis: Coding Agent / Developer Harness

Use this section for coding agents and developer tools such as Claude Code, Codex, Cursor, Windsurf, Copilot, Gemini CLI, and OpenCode.

## Codebase Context Model

- How does the agent discover relevant files?
- Does it use repo indexing, retrieval, open files, terminal state, git state, or explicit user selection?
- Does it support project-level instruction files such as `AGENTS.md`, `CLAUDE.md`, rules files, or equivalents?
- Does it understand monorepos, multiple worktrees, or multi-root workspaces?

## Developer Memory Model

- What persists across sessions?
- What is stored locally versus in a cloud account?
- Can the agent remember user preferences, repo conventions, and past decisions?
- Are memories explicit files, hidden product state, or both?
- Can teams share rules, prompts, skills, or project memory?

## Tool and Protocol Integration

- Does it support MCP or another tool protocol?
- Can external memory servers be attached?
- Does it expose tools for filesystem, terminal, browser, GitHub, Slack, Notion, or other systems?
- Can tool outputs become long-term memory?

## Execution and Safety Boundary

- What can the agent execute locally?
- How are permissions, approvals, sandboxing, and secrets handled?
- Can memory accidentally include private code, credentials, or local machine details?
- How transparent is the agent about what context it used?

## Coding Agent Comparison Axes

| Axis | Key question |
|---|---|
| Repo context | How does the agent find and use codebase context? |
| Instruction system | Are repo, user, and team instructions first-class? |
| Session persistence | What survives after a session ends? |
| External memory support | Can it connect to a memory layer through MCP/API/tools? |
| Team sharing | Can teams share context and conventions? |
| Local/cloud split | What lives on the machine versus in the vendor account? |
