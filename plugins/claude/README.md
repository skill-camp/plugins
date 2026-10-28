# Skill Camp plugin for Claude

Connects Claude to your trained Skill Camp skills. The plugin adds the Skill Camp MCP server (`https://mcp.skillcamp.sh/mcp`) and the `skill-camp` skill, which tells the agent to check your skills at the start of every new task.

## Install

In Claude Code, run these two commands:

```text
/plugin marketplace add skill-camp/plugins
/plugin install skillcamp@skill-camp
```

The same marketplace serves claude.ai, Claude Desktop, and Cowork. Check the install with `claude mcp list`: it lists `plugin:skillcamp:skillcamp: https://mcp.skillcamp.sh/mcp (HTTP)`. Sign in when asked; your agent will check your skills at the start of each new task.

## Try it against staging

The public marketplace only lists the production plugin. To try a staging server, run a local copy instead. From the repository root:

```bash
cp -r plugins/claude /tmp/skillcamp-staging
```

Edit `/tmp/skillcamp-staging/.mcp.json` so the server URL is `https://mcp.skill-camp.sh/mcp`, then start Claude with that copy:

```bash
claude --plugin-dir /tmp/skillcamp-staging
```

The copy loads for that session only; nothing is installed.
