# Threat Unknown for your coding agent

Scan a connected GitHub repository, read findings, check a package before adding it, and keep a feature's threat model up to date from your coding agent.

Threat Unknown checks source code, infrastructure definitions, and dependencies. Use the Threat Unknown portal to run penetration tests and request fixes. When Threat Unknown opens a fix pull request, a person reviews and merges it.

## Install

### Claude app

In Claude on desktop or web, open **Customize → Plugins → Add → Add marketplace**. Paste `https://github.com/ThreatUnknown/agent-plugin` and install **Threat Unknown**.

Open the plugin's **Connectors** tab. Choose **Connect** next to `threat-unknown` and sign in. If you see **Add**, choose it first.

If you do not see **Connect**, open **Settings → Connectors → Add custom connector**. Name it **Threat Unknown**, paste `https://mcp.threatunknown.com/v1/mcp`, and choose **Sign in now** and **Use Claude's published identity**.

### Claude Code

Install the plugin from your terminal.

```sh
claude plugin install threat-unknown --marketplace ThreatUnknown/agent-plugin
```

Open Claude Code. Run `/mcp`, choose `threat-unknown`, then select **Authenticate** to sign in.

To add just the connector, run this in your terminal and sign in through `/mcp`.

```sh
claude mcp add --transport http threat-unknown https://mcp.threatunknown.com/v1/mcp
```

### Codex

Run these in a terminal and sign in in your browser.

```sh
codex plugin marketplace add ThreatUnknown/agent-plugin
codex plugin add threat-unknown@threat-unknown
codex mcp login threat-unknown
```

If you use the Codex desktop app or the Codex extension in VS Code, you can add the connection and skills separately. Run these in a terminal.

```sh
codex mcp add threat-unknown --url https://mcp.threatunknown.com/v1/mcp
codex mcp login threat-unknown
npx skills add ThreatUnknown/agent-plugin
```

If `codex` is not found, install Codex first or run it using its full path.

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

**Open a new chat or session** after you sign in. Ask your agent:

> list my Threat Unknown findings

The plugin includes five skills.

- [Work safely with Threat Unknown](skills/threat-unknown-safety/SKILL.md)
- [Triage findings](skills/triage-findings/SKILL.md)
- [Scan a repository](skills/scan-a-repository/SKILL.md)
- [Check a package](skills/check-a-package/SKILL.md)
- [Threat-model a feature](skills/threat-model-a-feature/SKILL.md)

## License

[Apache License 2.0](LICENSE). The license does not grant use of the Threat Unknown name or logo.
