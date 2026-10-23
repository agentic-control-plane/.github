# Security policy

## Reporting a vulnerability

Please do not open a public issue for security problems.

1. **Preferred:** use GitHub's private vulnerability reporting on the affected repository: open the repo's **Security** tab and choose **Report a vulnerability**. The report is visible only to maintainers.
2. **Fallback:** if private reporting is unavailable for that repo, email **support@agenticcontrolplane.com** with `SECURITY` in the subject line.

Include what you can: the affected repo and version, steps to reproduce, impact, and any proof-of-concept. Please keep exploit details out of public channels (issues, discussions, social media) until a fix has shipped.

We will acknowledge your report, keep you informed as we work on it, and credit you in the fix if you would like.

## Supported versions

Only the latest release of each repository receives security fixes. The hosted installer at `agenticcontrolplane.com/install.sh` always serves the current release; run `acp-update` (or re-run the installer) to pick up fixes.

## Scope

Everything in the `agentic-control-plane` organization: the installer, agent plugins and hooks, the MCP server, the governance SDKs, and the hosted service at `agenticcontrolplane.com` / `api.agenticcontrolplane.com`.
