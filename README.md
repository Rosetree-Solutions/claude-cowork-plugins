# Claude Cowork Plugins

A collection of plugins for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) that bundle MCP server integrations with custom skills.

## Available Plugins

| Plugin                 | Description                                                                   |
|------------------------|-------------------------------------------------------------------------------|
| [lucid](plugins/lucid) | Connect to Lucid (Lucidchart & Lucidspark) for creating and managing diagrams |

## Installation

These plugins are designed for use with [Claude CoWork](https://claude.com/cowork). To install a plugin, run the following commands inside Claude Code:

1. **Add the marketplace:**
   ```
   /plugin marketplace add rosetree/claude-cowork-plugins
   ```

2. **Install a plugin:**
   ```
   /plugin install lucid@rosetree-lucid-plugin
   ```

3. **Authenticate:** The first time you use a plugin's MCP tools, you'll be prompted to connect your account (e.g., sign in to Lucid).

Once installed, the plugin's skills are available automatically. For example, ask Claude to "create a flowchart" or "find my Lucid diagrams" and the appropriate skill will activate.

## Plugin Structure

Each plugin lives in its own directory under `plugins/` and can include:

```
plugins/<plugin-name>/
├── .claude-plugin/
│   ├── plugin.json          # Plugin manifest (name, description, version, author)
│   └── marketplace.json     # Marketplace catalog for plugin distribution
├── .mcp.json                # MCP server configuration
├── .claude/
│   └── settings.local.json  # Permission allowlists for MCP tools
└── skills/
    └── <skill-name>/
        └── SKILL.md          # Skill definition with instructions for Claude
```

- **plugin.json** — Identifies the plugin and provides metadata (name, description, version, keywords).
- **marketplace.json** — Catalog file that registers the plugin for distribution via `/plugin marketplace add`.
- **.mcp.json** — Registers MCP servers (HTTP or stdio) that the plugin connects to.
- **settings.local.json** — Whitelists specific MCP tools and restricts external access (e.g., domain-scoped `WebFetch`).
- **SKILL.md** — Defines a skill with YAML front matter (`name`, `description`) and markdown instructions that guide Claude through a workflow using the plugin's MCP tools.

## Contributing a New Plugin

1. Create a directory: `plugins/<your-plugin-name>/`
2. Add a `.claude-plugin/plugin.json` with at minimum:
   ```json
   {
     "name": "your-plugin-name",
     "description": "What this plugin does",
     "version": "1.0.0",
     "author": { "name": "Your Name" }
   }
   ```
3. Add `.mcp.json` if your plugin uses an MCP server.
4. Add skills under `skills/<skill-name>/SKILL.md` for guided workflows.
5. Add `.claude/settings.local.json` to configure tool permissions.
6. Add a `.claude-plugin/marketplace.json` to register the plugin for distribution.
7. Update the **Available Plugins** table in this README.