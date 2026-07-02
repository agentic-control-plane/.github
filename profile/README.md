<p align="center">
  <img src="https://raw.githubusercontent.com/agentic-control-plane/.github/main/profile/assets/banner.png" alt="Agentic Control Plane" width="820" />
</p>

<h1 align="center">Agentic Control Plane</h1>

<p align="center"><strong>See, control, and optimize your AI agents — down to each tool call.</strong></p>

<p align="center">
  <a href="https://agenticcontrolplane.com">agenticcontrolplane.com</a> ·
  <a href="https://cloud.agenticcontrolplane.com/login">Dashboard</a> ·
  <a href="https://agenticcontrolplane.com/docs">Docs</a> ·
  <a href="https://agenticcontrolplane.com/trust">Trust &amp; security</a> ·
  <a href="https://agenticcontrolplane.com/install">Book a 30-min install</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/install-one%20command-5b5bd6" alt="One command install" />
  <img src="https://img.shields.io/badge/works%20with-Claude%20Code%20·%20Cursor%20·%20LangGraph%20·%20CrewAI%20·%20MCP-06b6d4" alt="Works with" />
  <img src="https://img.shields.io/badge/free%20tier-10k%20calls%2Fmo-16a34a" alt="Free tier" />
</p>

---

## Is this you?

You shipped an agent that calls real tools — refunds, database writes, emails, customer data — and now you can't fully **see** what it does, **stop** what it shouldn't, or explain the **bill**. You hand-rolled some checks, but they only hold while you're watching.

ACP is the layer that holds when you're not. One command, and every tool and model call your agents make becomes identified, policy-checked, priced, and logged — one panel, any framework, no code changes:

```
$ curl -sf https://agenticcontrolplane.com/install.sh | bash
  ✓ pr-reviewer connected · first governed call in 28s

  run #4821 · agent: pr-reviewer · acting for alice        cost     decision
  ──────────────────────────────────────────────────────────────────────────
  llm.plan          sonnet-4.5   1,840ms   9,912 tok       $0.09    allow
  web.search        ×3             240ms        —          free     allow
  crm.query         customer record             —          —        redact PII
  refund.create     $840 · unusual size         —          —        ask  ⏸
  db.drop_table                                 —          —        deny ⛔
  llm.synthesize    sonnet-4.5   2,110ms  12,400 tok       $0.11    allow
  ──────────────────────────────────────────────────────────────────────────
  7 calls · $0.31 · 1 redacted · 1 held for approval · 1 denied
```

Coding agents (Claude Code, Cursor) auto-install a hook. Framework agents (LangGraph, CrewAI, Vercel AI SDK, OpenAI Agents) drop in a package. ChatGPT / Claude Desktop add `mcp.agenticcontrolplane.com/mcp` as a connector.

---

## What you get

**See** — every tool call and model call in real time: who triggered it, which agent, what it returned, what it cost, how long it took. The black box becomes a readable, filterable, exportable log.

**Control** — allow, ask, redact, or deny, per operation, scoped by agent, agent type, role, or user. Deny-by-default on the destructive stuff (`rm -rf`, `DROP TABLE`, unbounded refunds). Enforced at the call, outside the model — so a prompt-injected or confused agent can't talk its way past it.

**Optimize** — the part most tools skip. ACP prices every call and breaks a run down step by step — loop vs. leaf — so you can see that one model call is most of the bill and route the cheap steps to a cheaper model. Same runs, three lenses: by agent, by model, by tool.

Plus: PII / secret redaction before data reaches the model, prompt-injection scanning, per-agent run variability (p50/p95, divergent runs), a team dashboard with roles, and audit mode — see everything, block nothing, until you're ready to enforce.

---

## The Three-Party Problem

AI apps have three actors — user, LLM, backend — but no shared identity layer. The backend sees a service token, not a person, so it can't tell who the agent is acting for.

```
        USER (Alice)
           │  ✓ Authenticated
           ▼
         LLM  ──────┐
           │        │   Every tool call:
           │        │    • Identified  • Authorized
           ▼        │    • Priced      • PII-scanned
     AGENTIC        │    • Audited     • Injection-checked
     CONTROL  ◀─────┘
      PLANE
           │
           ▼
       BACKEND / TOOLS
```

ACP sits at the tool-call boundary, binds every call to the identity of the user the agent is acting for, enforces policy, meters cost, and writes an attributable audit log. [Full explanation →](https://agenticcontrolplane.com/what-is-an-agentic-control-plane)

---

## Open source

The enforcement layer is MIT-licensed and runs in your infrastructure with or without us — so if we disappeared tomorrow, your control plane keeps running. ([Why that matters →](https://agenticcontrolplane.com/trust))

| Repo | What it is |
|------|------------|
| [**acp-install**](https://github.com/agentic-control-plane/acp-install) | One-command installer — governance hooks + MCP connectors for Claude Code, coding agents, and MCP clients. |
| [**acp-governance-sdks**](https://github.com/agentic-control-plane/acp-governance-sdks) | Drop-in SDKs (TypeScript + Python) — scoped subagents and delegation chains inside your framework code. |
| [**delegation-chain-spec**](https://github.com/agentic-control-plane/delegation-chain-spec) | ADCS — the open spec for agent-to-agent delegation with capability narrowing and a human sponsor at the root. |
| [**agentgovbench**](https://github.com/agentic-control-plane/agentgovbench) | 48-scenario benchmark testing identity, policy, and observability across agent frameworks. |
| [**GatewayStack**](https://github.com/davidcrowe/GatewayStack) | The governance runtime the above build on — identity, policy, limits, routing, redaction, audit as composable npm modules. |

The commercial control plane (hosted dashboard, team management, cost X-ray, policy engine) is closed source; the runtime, plugins, specs, and reference implementations are open.

---

## Pricing

- **Free** — 10,000 calls/month, unlimited agents &amp; seats, full see / control / optimize.
- **Pro ($29.99/mo)** — 100,000 calls, per-user limits, custom PII patterns, 90-day retention.
- **Team ($299.99/mo flat)** — 1M calls, roles/RBAC, org-wide cost rollup, unlimited seats, 1-year retention.
- **Enterprise** — SSO, VPC / self-host, unlimited retention. [Talk to us](https://agenticcontrolplane.com/pricing).

[Full pricing →](https://agenticcontrolplane.com/pricing) · [Start free →](https://cloud.agenticcontrolplane.com/login)

---

## Community &amp; contact

- **Blog / writing** → [agenticcontrolplane.com/writing](https://agenticcontrolplane.com/writing)
- **What we see &amp; store, exit path, security posture** → [agenticcontrolplane.com/trust](https://agenticcontrolplane.com/trust)
- **Want it installed with you?** → [book 30 minutes](https://agenticcontrolplane.com/install) — a working session, not a pitch
- **Report a security issue** → [security.txt](https://agenticcontrolplane.com/.well-known/security.txt) or david@agenticcontrolplane.com
- **Everything else** → open an issue on the relevant repo, or email david@agenticcontrolplane.com

<p align="center"><sub>© Reducibl · <a href="https://agenticcontrolplane.com/privacy">Privacy</a> · <a href="https://agenticcontrolplane.com/terms">Terms</a></sub></p>
