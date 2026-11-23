# Decisions — OpenCode

Last updated: 2026-11-23 20:44:23 +06:00 (Asia/Dhaka) — `Update-files` run.

- 2026-11-19: Communication is file-based (messages + tasks under
  `agents/`); no central broker — agents scan folders and handle what is
  addressed to them or `all`.
- 2026-11-19: Git repo for the common folder `~/Public/Agents` (local init;
  remote to be added). See
  [plans/centralized_agentic_system.md](../plans/centralized_agentic_system.md).
- 2026-11-19 23:01:54 +06:00: `Update-files` is a standing command from Arnob.
  Rationale: a single trigger keeps every workspace file current (dates,
  timestamps, work log, session record, todos) and produces a consistent
  affirmation. Defined in
  [protocols/update_files.md](../protocols/update_files.md).
- 2026-11-19 23:09:35 +06:00: Auto-update is session-scoped, not scheduled.
  Rationale: Arnob wants files refreshed only while we're actively working
  together — no cron/systemd timer, daemon or token-burning background runs.
  See [protocols/auto_update.md](../protocols/auto_update.md).
- 2026-11-20 12:13:51 +06:00: Full `Update-files` runs are committed and
  pushed with `[opencode]` attribution. Rationale: the shared repo is now
  synced with GitHub, so other agents should see refreshed state and who did
  the work.
- 2026-11-23 20:44:23 +06:00: Keep the workspace module set aligned across
  agents (OpenCode's `skills/` and `plugins/` added 20:42:26) while retaining
  OpenCode V2-specific facts. Rationale: consistency in the shared repo helps
  other agents; accuracy about tool compatibility comes from official docs.
