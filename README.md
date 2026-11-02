# Untopple plugin

Build, run and repair automations with [Untopple](https://untopple.com) from Claude.

The plugin adds the Untopple connector and a skill that tells Claude how to build an automation: understand what you want, research it, then build it in a draft. Everything runs on Untopple, so nothing is installed on your computer.

## Install

### Claude app

1. Open **Customize**, then **Plugins**, and add a marketplace from GitHub: `untopple/claude-plugin`.
2. Install **untopple**.
3. Open the plugin's **Connectors** tab and choose **Connect**, then sign in with your Untopple account.

### Claude Code

```
/plugin marketplace add untopple/claude-plugin
/plugin install untopple@untopple
```

Then run `/mcp`, pick untopple and sign in.

### For a team

Add this to your repository's `.claude/settings.json`, and everyone who opens it in Claude Code is offered the plugin:

```json
{
  "extraKnownMarketplaces": {
    "untopple": { "source": { "source": "github", "repo": "untopple/claude-plugin" } }
  },
  "enabledPlugins": { "untopple@untopple": true }
}
```

## Other agents

Cursor, VS Code, Codex and others connect to `https://untopple.com/api/mcp` directly. See [untopple.com](https://untopple.com/#connect).
