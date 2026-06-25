<p align="center">
  <img src="https://raw.githubusercontent.com/agentic-control-plane/.github/main/profile/assets/banner.png" alt="Agentic Control Plane" width="820" />
</p>

<h1 align="center">Agentic Control Plane</h1>

<p align="center"><strong>Every tool call your AI makes — logged, governed, and visible to your team.</strong></p>

<p align="center">
  <a href="https://agenticcontrolplane.com">agenticcontrolplane.com</a> ·
  <a href="https://cloud.agenticcontrolplane.com/login">Dashboard</a> ·
  <a href="https://agenticcontrolplane.com/docs">Docs</a> ·
  <a href="https://agenticcontrolplane.com/what-is-an-agentic-control-plane">What is an ACP?</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/install-one%20command-5b5bd6" alt="One command install" />
  <img src="https://img.shields.io/badge/clients-Claude%20Code%20·%20OpenClaw%20·%20ChatGPT%20·%20Cursor%20·%20MCP-06b6d4" alt="Clients supported" />
  <img src="https://img.shields.io/badge/free%20tier-unlimited%20logging-16a34a" alt="Free tier" />
</p>

---

## Control your AI

AI agents don't just chat anymore. They act — reading your data, writing to your tools, running your commands. Some tool calls contain PII. Some carry prompt-injection payloads from content you never vetted. Some run while you sleep.

**Tool calls are where risk becomes real. So that's where we govern.**

```bash
curl -sf https://agenticcontrolplane.com/install.sh | bash
```

One command auto-detects Claude Code and OpenClaw, installs a governance hook, opens your browser to log in, and starts logging in 30 seconds. For ChatGPT, Claude Desktop, and Lovable, add `mcp.agenticcontrolplane.com/mcp` as a connector.

<p align="center">
  <img src="https://raw.githubusercontent.com/agentic-control-plane/.github/main/profile/assets/dashboard-overview.png" alt="ACP dashboard — overview" width="820" />
</p>

---

## What you get

- **Activity log** — every Bash command, file write, web fetch, and MCP tool call, in real time with identity, arguments, and timestamps.
- **Policies by agent tier** — interactive, subagent, background, and API agents get different rules. Per-tool overrides for anything sensitive.
- **Data protection** — detect and redact PII, API keys, and secrets in tool inputs before they reach downstream services.
- **Prompt-injection detection** — post-hook scans flag adversarial patterns in tool responses.
- **Team visibility** — one dashboard for the whole team. See who called what, set policies that apply to everyone.
- **Audit mode** — see everything, block nothing. Switch to enforce when you're ready.

---

## The Three-Party Problem

AI apps have three actors — user, LLM, backend — but no shared identity layer.

```
        USER (Alice)
           │
           │  ✓ Authenticated
           ▼
         LLM  ──────┐
           │        │
           │        │  Every tool call:
           │        │   • Identified
           ▼        │   • Authorized
     AGENTIC        │   • Audited
     CONTROL  ◀─────┘   • PII-scanned
      PLANE             • Injection-checked
           │
           ▼
       BACKEND / TOOLS
```

ACP sits at the tool-call boundary. It verifies identity, enforces policy, redacts sensitive data, and writes an immutable audit log — so every AI action is attributable, authorized, and auditable.

[Full explanation →](https://agenticcontrolplane.com/what-is-an-agentic-control-plane)

---

## The ecosystem

ACP is built on top of [GatewayStack](https://github.com/davidcrowe/GatewayStack) — our open-source AI governance runtime.

| Repo | What it is |
|------|------------|
| [**GatewayStack**](https://github.com/davidcrowe/GatewayStack) | Open-source AI governance runtime — identity, policy, rate limits, routing, audit. Six modular npm packages. |
| [**claude-code-acp-plugin**](https://github.com/davidcrowe/claude-code-acp-plugin) | Governance plugin for Claude Code. |
| [**openclaw-acp-plugin**](https://github.com/davidcrowe/openclaw-acp-plugin) | Governance plugin for OpenClaw. |
| [**gatewaystack-chatgpt-starter**](https://github.com/davidcrowe/gatewaystack-chatgpt-starter) | Open-source MCP server starter with OAuth identity and JWT verification. |

The ACP commercial control plane (dashboard, team management, policy engine) is closed source. The runtime, plugins, and reference implementations are open.

---

## Pricing

- **Free** — unlimited tool-call logging, policy enforcement, data protection. For individuals.
- **Team** — per-member activity, per-client and per-user policies. Free during beta.

[Start free →](https://cloud.agenticcontrolplane.com/login)

---

## Community & contact

- **Blog / writing** → [agenticcontrolplane.com/writing](https://agenticcontrolplane.com/writing)
- **Report a security issue** → see [SECURITY.md](https://github.com/davidcrowe/GatewayStack/blob/main/SECURITY.md) in GatewayStack
- **Everything else** → open an issue on the relevant repo above, or email via the contact on [agenticcontrolplane.com](https://agenticcontrolplane.com)

<p align="center"><sub>© Reducibl · <a href="https://agenticcontrolplane.com/privacy">Privacy</a> · <a href="https://agenticcontrolplane.com/terms">Terms</a></sub></p>
