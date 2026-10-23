# Getting help

Agentic Control Plane (ACP) is spread across several repositories in this organization. The fastest route to a fix is to tell us what broke, where.

## Where to ask

- **Something in a specific repo is broken** (installer, a plugin, the MCP server, an SDK): open an issue on **that repo**. Each repo's Issues tab is the canonical queue and is watched.
- **Not sure which repo, account or billing questions, or anything you'd rather not post publicly:** email **support@agenticcontrolplane.com**.
- **Security concerns:** see [SECURITY.md](SECURITY.md). Do not file a public issue.

## What to include

The more of this you give us up front, the fewer round trips:

- **OS and version** (e.g. macOS 15.3, Ubuntu 24.04) and `node --version`.
- **Which agent(s)** you are running (Claude Code, Cursor, Codex CLI, Copilot, OpenClaw, opencode, Qwen Code, pi, Prime Agent, Muse Code, Grok Build, Antigravity, Hermes Agent, DeepSeek Harness) and their versions.
- **The full installer or command output**, copied from your terminal. Error text beats a screenshot.
- Whether you installed in connected mode (default) or `--local`.
- What you expected to happen and what happened instead.

Please redact anything sensitive (API keys, tokens from `~/.acp/credentials`) before posting.

## Docs

- Getting started: https://agenticcontrolplane.com/getting-started
- Every file the installer writes: https://agenticcontrolplane.com/install-explained
- Per-agent integration guides: https://agenticcontrolplane.com/integrations
- FAQ: https://agenticcontrolplane.com/faq
