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

## What you get with `strata`

The [`strata` plugin](https://github.com/strata-space/strata-claude-plugin) lets
you mount your Strata Spaces as local Markdown folders and work with your Strata
documents right inside a conversation through its bundled MCP server. It ships
five skills:

- **strata-spaces** — mount or sync a Strata Space as a local folder of Markdown
- **strata-research** — answer questions from your knowledge base, with citations
- **strata-publish** — push local content up into Strata
- **strata-review** — leave anchored comments on a document without rewriting it
- **strata-doctor** — diagnose Strata connectivity and write failures

See the [plugin README](https://github.com/strata-space/strata-claude-plugin) for
full documentation.

### Optional: the Strata CLI

The filesystem and mount features need the Strata CLI. Install it with:

```
brew install --cask strata-space/strata/strata
```

The plugin can also install it for you on first run. See
[Install the Strata CLI](https://github.com/strata-space/strata-claude-plugin#install-the-strata-cli-optional)
for details.

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
