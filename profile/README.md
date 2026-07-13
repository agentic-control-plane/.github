<p align="center">
  <img src="https://raw.githubusercontent.com/agentic-control-plane/.github/main/profile/assets/banner.png" alt="Agentic Control Plane" width="820" />
</p>

<h1 align="center">Agentic Control Plane</h1>

<p align="center"><strong>See, control, and optimize your AI agents — down to each tool call.</strong></p>

<p align="center">
  <a href="https://agenticcontrolplane.com">Website</a> ·
  <a href="https://cloud.agenticcontrolplane.com/login">Live dashboard</a> ·
  <a href="https://agenticcontrolplane.com/docs">Docs</a> ·
  <a href="https://agenticcontrolplane.com/trust">Trust &amp; security</a> ·
  <a href="https://agenticcontrolplane.com/install">Book a 30-min install</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/enforcement%20layer-MIT%20licensed-16a34a" alt="MIT licensed" />
  <img src="https://img.shields.io/badge/runs-anywhere%20·%20self--hostable-5b5bd6" alt="Self-hostable" />
  <img src="https://img.shields.io/badge/works%20with-Claude%20Code%20·%20Cursor%20·%20LangGraph%20·%20CrewAI%20·%20MCP-06b6d4" alt="Works with" />
</p>

---

ACP is the layer between your AI agents and the systems they touch. It sits in the runtime call path and makes every tool and model call **identified, policy-checked, priced, and logged** — across any framework, with one install and no code changes. When an agent tries to refund the wrong customer, delete the wrong table, or quietly run up the bill, this is the layer that sees it and stops it.

We run our own production agents through it. The dashboard below is a real workspace:

<p align="center">
  <img src="https://raw.githubusercontent.com/agentic-control-plane/.github/main/profile/assets/dashboard-overview.png" alt="ACP dashboard — every agent's calls, cost, denials, and run-to-run variability in one view" width="860" />
</p>

## Try it in 30 seconds

```bash
curl -sf https://agenticcontrolplane.com/install.sh | bash
```

Auto-detects Claude Code and other coding agents, drops in a governance hook, and shows your first governed call in about 30 seconds. Other paths:

- **Framework agents** (LangGraph, CrewAI, Vercel AI SDK, OpenAI Agents) → drop in a package, wrap your tools.
- **MCP clients** (ChatGPT, Claude Desktop) → add `mcp.agenticcontrolplane.com/mcp` as a connector.
- **Anything else** → call the governance API directly with a bearer token.

## What it does

| | |
|---|---|
| **See** | Every tool + model call in real time — who triggered it, which agent, what it returned, what it cost, how long it took. Filterable, exportable, attributable. |
| **Control** | Allow / ask / redact / deny, per operation, scoped by agent, agent type, role, or user. Deny-by-default on the destructive stuff. Enforced at the call, outside the model — so a prompt-injected agent can't talk its way past it. |
| **Optimize** | Every call priced, every run broken down loop-vs-leaf, so you can see which step is the bill and route the cheap steps to a cheaper model. Plus per-agent run variability (p50/p95) to catch the flaky one. |

## Open source

The enforcement layer is **MIT-licensed and runs in your infrastructure** — so if we disappeared tomorrow, your control plane keeps running. That's the whole point: putting a vendor in your agents' call path should never be a lock-in. ([Why that matters →](https://agenticcontrolplane.com/trust))

| Repo | What it is |
|------|------------|
| [**acp-install**](https://github.com/agentic-control-plane/acp-install) | One-command installer — governance hooks + MCP connectors for coding agents and MCP clients. |
| [**acp-governance-sdks**](https://github.com/agentic-control-plane/acp-governance-sdks) | Drop-in SDKs (TypeScript + Python) — scoped subagents and delegation chains inside your framework code. |
| [**delegation-chain-spec**](https://github.com/agentic-control-plane/delegation-chain-spec) | **ADCS** — the open spec for agent-to-agent delegation: capability narrowing, a human sponsor at the root of every chain, per-hop scope intersection. |
| [**hermes-acp-plugin**](https://github.com/agentic-control-plane/hermes-acp-plugin) | Native Python plugin for Nous Research's Hermes Agent — `pip install hermes-acp`, every tool call governed. |
| [**acp-pr-reviewer-demo**](https://github.com/agentic-control-plane/acp-pr-reviewer-demo) | Worked A2A example — a PR reviewer delegating to scoped sub-agents, every hop audited. |
| [**agentgovbench**](https://github.com/agentic-control-plane/agentgovbench) | 48-scenario benchmark testing identity, policy, and observability across agent frameworks. |
| [**GatewayStack**](https://github.com/agentic-control-plane/GatewayStack) | The runtime the above build on — identity, policy, limits, routing, PII redaction, audit as composable npm modules. |

The hosted control plane (dashboard, team management, cost X-ray, policy engine) is closed source; the runtime, plugins, specs, and reference implementations are open and auditable.

## The problem underneath it

AI apps have three actors — user, LLM, backend — with no shared identity layer. The backend sees a service token, not a person, so it can't tell who the agent is acting for, whether the action was authorized, or what it cost.

```
   USER ─auth→ LLM ─────► AGENTIC CONTROL PLANE ─────► BACKEND / TOOLS
                          every call: identified · authorized
                          priced · PII-scanned · audited
```

ACP closes that gap at the tool-call boundary. [The full argument →](https://agenticcontrolplane.com/what-is-an-agentic-control-plane)

## Pricing

Free for individuals (10k calls/mo, unlimited agents &amp; seats). Pro **$29.99/mo**, Team **$299.99/mo flat** (unlimited seats), Enterprise for SSO + self-host. [Full pricing →](https://agenticcontrolplane.com/pricing)

## Contact

Blog → [agenticcontrolplane.com/writing](https://agenticcontrolplane.com/writing) · Trust &amp; security → [/trust](https://agenticcontrolplane.com/trust) · Security disclosure → [security.txt](https://agenticcontrolplane.com/.well-known/security.txt) · Everything else → david@agenticcontrolplane.com

<p align="center"><sub>© Reducibl · <a href="https://agenticcontrolplane.com/privacy">Privacy</a> · <a href="https://agenticcontrolplane.com/terms">Terms</a></sub></p>
