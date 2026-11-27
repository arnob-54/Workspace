# Plugins — OpenCode

Plugins that extend OpenCode with tools, hooks, commands, agents and UI parts.
Official docs: https://opencode.ai/docs/plugins/ and
https://opencode.ai/docs/build/plugins/

## Install and manage

```sh
opencode plugin add <package>          # npm name, version/range, or Git spec
opencode plugin list --builtin
opencode plugin list
opencode plugin check
opencode plugin update
opencode plugin remove <package>
```

## Discovery and configuration

- `.opencode/plugins/` (project) and `~/.config/opencode/plugins/` (global)
  auto-load `.ts`/`.js` files and immediate plugin package directories.
- Published packages, versioned packages and local directories can also be
  listed in the `plugins` array of `opencode.jsonc`.
- TUI-only plugins are configured separately in `cli.json`.

## Compatibility note

OpenCode plugins are built against `@opencode/plugin` (server/TUI/GUI/RPC
parts). The official V2 docs do **not** list Claude Code plugin manifests
(`.claude-plugin/plugin.json`, `hooks.json`, `mcp_config.json`) as a supported
plugin source. Claude Code **skills**, however, are discovered through
`~/.claude/skills` and `.claude/skills`.

This folder records plugins relevant to this workspace; to load one, install
it with the CLI or configure it as described above.

## MCP servers (separate from plugins)

OpenCode supports the Model Context Protocol directly. Official docs:
https://opencode.ai/docs/mcp-servers/

- Register a remote server with `opencode mcp add <name> --url <https-url>`, or
  a local stdio server with `opencode mcp add <name> -- <command> ...`.
- Configuration lives in `opencode.jsonc` under `mcp.servers` (add `--global`
  to the CLI for global scope): `type: local` with `command`, `cwd` and
  `environment`, or `type: remote` with `url`, `headers` and `oauth`.
- Remote servers use OAuth by default; `/mcps` handles sign-in. MCP prompts
  become `/<server>:<prompt>` commands, and resources are read through the
  built-in resource tools.
- Claude Code's `.mcp.json` is **not** documented as auto-imported. The same
  MCP server can be reused, but its command/URL/headers must be registered in
  OpenCode's format.

**Last updated:** 2026-11-27 23:30:27 +06:00 (Asia/Dhaka) — `Update-files` run;
discovery, compatibility and MCP notes re-verified unchanged. Current state:
0 plugins recorded yet.
