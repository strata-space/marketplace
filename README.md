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
| [`strata`](https://github.com/strata-space/strata-claude-plugin) | Keep Strata Spaces in live two-way sync as local Markdown folders, and work with your Strata documents in conversation through the bundled MCP server: research with citations, publish local content, review with comments, and diagnose connectivity. |
| [`strata-memory`](https://github.com/strata-space/strata-memory-plugin) | Turn a Strata Space into your coding agent's long-term memory: recall on every prompt, an update contract, and a stop-time nudge to write back what changed. Works in Claude Code and Codex. |

Install a specific plugin directly:

```
/plugin install strata@strata-space
/plugin install strata-memory@strata-space
```

## What you get with `strata`

The [`strata` plugin](https://github.com/strata-space/strata-claude-plugin) lets
you keep your Strata Spaces in live two-way sync as local Markdown folders and
work with your Strata documents right inside a conversation through its bundled
MCP server. It ships five skills:

- **strata-spaces** — link a Strata Space to a local folder for live two-way sync (or mount it as a drive)
- **strata-research** — answer questions from your knowledge base, with citations
- **strata-publish** — push local content up into Strata
- **strata-review** — leave anchored comments on a document without rewriting it
- **strata-doctor** — diagnose Strata connectivity and write failures

See the [plugin README](https://github.com/strata-space/strata-claude-plugin) for
full documentation.

### Optional: the Strata CLI

The filesystem features (live sync and mount) need the Strata CLI. Install it with:

```
brew install --cask strata-space/tap/strata
```

The plugin can also install it for you on first run. See
[Install the Strata CLI](https://github.com/strata-space/strata-claude-plugin#install-the-strata-cli-optional)
for details.

## What you get with `strata-memory`

The [`strata-memory` plugin](https://github.com/strata-space/strata-memory-plugin)
makes a Strata Space your coding agent's long-term memory. On every prompt it
hybrid-searches the bound Space and surfaces relevant documents; the agent is
held to a standing contract to update any document whose facts its work
changed, with a gentle stop-time nudge when it forgets. Recall is fail-open:
a slow or unreachable backend never delays your prompt.

It requires the Strata CLI (3.3.0+, same brew install as above). Bind a Space
with `strata memory init`, or ask your agent to run the **strata-memory-init**
skill. It also works in Codex; see the
[plugin README](https://github.com/strata-space/strata-memory-plugin) for both
hosts' install steps.

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
