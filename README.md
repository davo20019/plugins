# davo20019 plugins

A plugin marketplace for Claude Code and Codex. Each plugin lives in its own repository; this repo is the
catalogue that lists them. Add it once, then install any plugin as `<plugin>@davo20019`.

## Add the marketplace

| Agent | Command |
|---|---|
| Claude Code | `/plugin marketplace add davo20019/plugins` |
| Codex | `codex plugin marketplace add davo20019/plugins` |

## Plugins

| Plugin | What it does | Install |
|---|---|---|
| [building-3d-replicas](https://github.com/davo20019/building-3d-replicas) | Exact 3D replicas of real objects from photos: code-CAD, cameras fitted to the photos, measurement, headless Blender, GLB | Claude Code: `/plugin install building-3d-replicas@davo20019`<br>Codex: `codex plugin add building-3d-replicas@davo20019` |

Updates: `claude plugin update <plugin>@davo20019` in Claude Code (or turn on auto-update for this
marketplace in `/plugin`); `codex plugin marketplace upgrade` then reinstall in Codex.

## Adding a plugin (for the maintainer)

1. The plugin's repo has `.claude-plugin/plugin.json` and `.codex-plugin/plugin.json` with the same `name`.
2. Add an entry to both catalogues: `.claude-plugin/marketplace.json` (source `github`, `owner/repo`) and
   `.agents/plugins/marketplace.json` (source `url`, the repo's `.git` URL; Codex rejects `github` and `git`).
3. Run `claude plugin validate .`, add a row to the table above, push.
