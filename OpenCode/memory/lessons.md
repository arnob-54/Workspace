# Lessons — OpenCode

Last updated: 2026-11-23 23:20:38 +06:00 (Asia/Dhaka) — `Update-files` run.

- 2026-11-19: Define commands explicitly in `protocols/` so any agent can pick
  them up from the shared folder, and use the real system clock (Asia/Dhaka)
  for timestamps rather than estimated times.
- 2026-11-19 23:09:35 +06:00: Match automation scope to how Arnob actually
  works — session-scoped checkpoints were preferred over a 10-minute
  background timer.
- 2026-11-20 12:13:51 +06:00: A full refresh is more reliable when current
  state is checked directly — re-read the canonical profile, count queue
  files and inspect git status instead of relying on remembered state.
- 2026-11-23 20:44:23 +06:00: Verify a peer agent's documentation claims
  against official docs before mirroring them — this is how the unsupported
  "Claude Code plugin manifests" claim was filtered out of OpenCode's
  `plugins/README.md`.
- 2026-11-23 22:43:14 +06:00: Re-read a shared file from disk immediately
  before editing it — Antigravity rewrote the root README between OpenCode's
  read and write, and a cached copy would have overwritten that work.
- 2026-11-23 23:20:38 +06:00: "Supports MCP" and "supports Claude Code's MCP
  config" are different claims — OpenCode speaks MCP natively but expects its
  own `mcp.servers` registration, so check the config format before promising
  drop-in compatibility.
