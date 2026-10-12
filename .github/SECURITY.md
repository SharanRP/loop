# Security policy

loop runs model-generated shell commands, edits files and starts MCP servers on real machines. We treat security reports as a high priority.

## Supported versions

loop is a developer preview (alpha). We fix security issues only in the latest release.

| Version | Supported |
|---|---|
| Latest release | Yes |
| Older releases | No |

## Report a vulnerability

**Do not open a public issue, discussion or pull request for a vulnerability.**

Report it privately with GitHub private vulnerability reporting:

1. Go to the [Security tab](https://github.com/soketlabs/loop/security) of this repository.
2. Click **Report a vulnerability**.
3. Fill in the form.

Direct link: <https://github.com/soketlabs/loop/security/advisories/new>

Include:

- The affected version (`loop --version`) or commit SHA.
- Your OS, architecture and install method.
- Steps to reproduce, or a proof of concept.
- The impact: what an attacker can do.
- Related settings, for example `toolPermissions`, `sandbox.mode` or MCP servers.

Remove API keys and other secrets from logs before you send them.

## In scope

- Sandbox escapes, and sandboxes that silently fall back to host execution.
- Tool approval bypasses, including prompt injection that leads to an unapproved action.
- Credential leaks: API keys or OAuth tokens in logs, traces, session files or tool subprocesses.
- Network listeners (for example `mcp-serve`) that are reachable without authentication from other hosts.
- `install.sh`, release artifacts, checksums and the release pipeline.

## Out of scope

- Actions that you approved, or that your settings allow (for example `toolPermissions` set to `allow`).
- Problems in a third-party model provider or MCP server that loop does not ship.
- Reports that need an attacker who already controls your machine or your loop config folder.

## What happens next

1. We acknowledge your report.
2. We confirm the issue and assess its severity.
3. We fix it in a new release and publish a GitHub Security Advisory.
4. We credit you in the advisory, unless you ask us not to.

Please do not disclose the issue in public until the advisory is published.
