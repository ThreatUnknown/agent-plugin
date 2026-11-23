# Threat Unknown for your coding agent

Scan a connected GitHub repository, read findings, check a package before adding it, and keep a feature's threat model up to date from your coding agent.

Threat Unknown checks source code, infrastructure definitions, and dependencies. Use the Threat Unknown portal to run penetration tests and request fixes. When Threat Unknown opens a fix pull request, a person reviews and merges it.

## Install

### Claude Code

Run these in Claude Code, then open `/mcp`, choose `threat-unknown`, and sign in.

```text
/plugin marketplace add ThreatUnknown/agent-plugin
/plugin install threat-unknown@threat-unknown
```

### Codex

Run these in a terminal, complete sign-in in your browser, then start a new Codex session.

```sh
codex plugin marketplace add ThreatUnknown/agent-plugin
codex plugin add threat-unknown@threat-unknown
codex mcp login threat-unknown
```

For a Codex client without plugin support, add the connection and skills separately.

```sh
codex mcp add threat-unknown --url https://mcp.threatunknown.com/v1/mcp
codex mcp login threat-unknown
npx skills add ThreatUnknown/agent-plugin --agent codex
```

### Cursor

If your team lists Threat Unknown in **Customize**, choose **Install**. Otherwise, add the skills in a terminal.

```sh
npx skills add ThreatUnknown/agent-plugin --agent cursor
```

Add this entry to your existing `~/.cursor/mcp.json`, or use it to create the file.

```json
{
  "mcpServers": {
    "threat-unknown": {
      "url": "https://mcp.threatunknown.com/v1/mcp"
    }
  }
}
```

Open the server in **Customize** and sign in when prompted.

### VS Code with GitHub Copilot

In the Command Palette, run **Chat: Install Plugin from Source** and paste `https://github.com/ThreatUnknown/agent-plugin`. Sign in when prompted.

### Gemini CLI

Run this in a terminal. Then open Gemini and run `/mcp auth threat-unknown` to sign in.

```sh
gemini extensions install https://github.com/ThreatUnknown/agent-plugin
```

### Other agents

```sh
npx skills add ThreatUnknown/agent-plugin
```

Add `https://mcp.threatunknown.com/v1/mcp` in your agent's server settings and sign in.

## Try it

Sign in with your Threat Unknown account. Your role controls what your agent can do. Start with a read-only question in a connected repository.

> What did Threat Unknown find in this repository, and what should I fix first?

The plugin includes five skills.

- [Work safely with Threat Unknown](skills/threat-unknown-safety/SKILL.md)
- [Triage findings](skills/triage-findings/SKILL.md)
- [Scan a repository](skills/scan-a-repository/SKILL.md)
- [Check a package](skills/check-a-package/SKILL.md)
- [Threat-model a feature](skills/threat-model-a-feature/SKILL.md)

## License

[Apache License 2.0](LICENSE). The license does not grant use of the Threat Unknown name or logo.
