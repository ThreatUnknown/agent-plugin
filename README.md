# Threat Unknown for your coding agent

Scan a connected GitHub repository, read findings, check a package before adding it, and keep a feature's threat model up to date from your coding agent.

Threat Unknown checks source code, infrastructure definitions, and dependencies. Your agent can ask Threat Unknown to fix a finding, or fix it itself from our suggested fix, and can follow and stop a penetration test. Starting a penetration test stays in the Threat Unknown portal. When Threat Unknown opens a fix pull request, a person reviews and merges it.

## Skills

Your agent reads these when they apply:

- `threat-unknown-safety`: the rules for every Threat Unknown call.
- `check-your-changes`: check what you changed before you say the work is done.
- `before-you-commit-push-or-deploy`: check your changes before a commit, a push, a pull request or a deploy.
- `scan-a-repository`: scan the branch you pushed before the pull request.
- `check-a-package`: check an npm package before you add, upgrade or start using it.
- `triage-findings`: sort findings into real problems, accepted risks and gaps.
- `fix-a-finding`: ask Threat Unknown to open a fix, or make the fix yourself from our suggested fix.
- `pen-test-status`: follow a penetration test, read its report, or stop it.
- `threat-model-a-feature`: write a feature's threat model and keep it current, and ask for a risk to be accepted through a pull request.

## Install

### Claude app

1. In the left sidebar, click **Plugins**. In the top right, click **Add**, then **Add marketplace**. Enter `ThreatUnknown/agent-plugin`.
2. On the plugin listing, click **Add to this computer**.
3. Open the plugin's `threat-unknown` connector and click **Connect**. Sign in to Threat Unknown in your browser.

   If there is no **Connect** button, click **Plugins**, **Add**, then **Add custom connector**. Type `Threat Unknown` in the first box and enter `https://mcp.threatunknown.com/v1/mcp` as the address. **Continue** stays grey until both boxes are filled. Click **Continue**.

   On the next screen, the defaults are marked **Detected**. **Keep these defaults**.

   - **Authentication** is **Sign in now**.
   - **OAuth client** is **Use Claude's published identity**.

   Click **Continue**. Your browser opens. Sign in to Threat Unknown to finish connecting.

4. **Start a new chat** and ask:

   > list my Threat Unknown findings

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
