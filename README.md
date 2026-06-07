# Strata plugins for Claude Code

The official [Claude Code](https://code.claude.com) plugin marketplace published by [Strata](https://strata.space).

## Add the marketplace

```
/plugin marketplace add strata-space/marketplace
```

Then browse and install plugins:

```
/plugin
```

## Available plugins

| Plugin | Description |
| --- | --- |
| [`strata`](https://github.com/strata-space/strata-claude-plugin) | Mount Strata Spaces as local Markdown folders, and work with your Strata documents in conversation through the bundled MCP server: research with citations, publish local content, review with comments, and diagnose connectivity. |

Install a specific plugin directly:

```
/plugin install strata@strata-space
```

## How this is organized

This repository is a **thin marketplace**: it holds only the marketplace manifest
(`.claude-plugin/marketplace.json`) and references each plugin by its own
repository. Plugins are versioned and released independently in their own repos —
this repo just lists them.

To add a plugin, append an entry to the `plugins` array in
`.claude-plugin/marketplace.json` pointing at its repository:

```jsonc
{
  "name": "your-plugin",
  "source": { "source": "github", "repo": "strata-space/your-plugin-repo" },
  "description": "…",
  "category": "…"
}
```

## License

[MIT](./LICENSE)
