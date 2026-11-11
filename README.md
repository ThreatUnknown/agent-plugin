# Threat Unknown for your agent

Connect the agent you already use to Threat Unknown. Ask it about your findings and
security plan, start and follow our security agents, and review changes waiting for your
approval.

This adds two things to your agent:

- **The Threat Unknown connection**: `https://mcp.threatunknown.com/v1/mcp`.
- **Five skills**, plain instructions your agent reads when they apply:
  - `threat-unknown-safety`: the rules for every Threat Unknown call.
  - `review-pending-approvals`: go through what is waiting for approval, one item at a time.
  - `triage-findings`: sort findings into real problems, accepted risks and gaps.
  - `run-a-security-agent`: start one of our agents, follow it and answer its questions.
  - `threat-model-a-feature`: write a feature's threat model and keep it current, and ask for a
    risk to be accepted through a pull request.

There is no code here. Nothing runs on your computer.

## Install

**Claude Code**

```
/plugin marketplace add ThreatUnknown/agent-plugin
/plugin install threat-unknown@threat-unknown
```

**Cursor, VS Code with Copilot, Codex**: install from this repository's address,
`https://github.com/ThreatUnknown/agent-plugin`.

- Cursor: Customize, then Install.
- VS Code: run **Chat: Install Plugin From Source** and paste the address.
- Codex: `codex plugin marketplace add ThreatUnknown/agent-plugin`, then `/plugins`.

**Gemini CLI**

```
gemini extensions install https://github.com/ThreatUnknown/agent-plugin
```

**Any other agent that reads skills**

```
npx skills add ThreatUnknown/agent-plugin
```

Then add the connection above in that agent's own settings.

## Signing in

The first time your agent calls Threat Unknown, it opens a browser. Sign in with your
Threat Unknown account. There are no keys to copy.

## What your agent can do

Your agent acts as you. It can do what your role in Threat Unknown allows, and nothing
more. If your role changes, so does what your agent can do, within minutes.

That includes approvals: if you can approve changes, so can your agent. Nothing changes in
your accounts without an approval, and approving a change that cannot be undone has to say
so explicitly. The skills tell your agent to ask you first. They are guidance, not the
safeguard: Threat Unknown checks every request itself.

To disconnect, remove the server from your agent or sign out there. Anyone removed from
your team loses their agent's access too.

## License

Apache License 2.0. See [LICENSE](LICENSE). The license does not grant use of the Threat Unknown name or logo.
