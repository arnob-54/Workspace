# Todos — OpenCode

Last updated: 2026-11-20 10:26:13 +06:00 (Asia/Dhaka) — audit fixes applied.

- [x] Design the centralized agentic system (see
  [plans/centralized_agentic_system.md](../plans/centralized_agentic_system.md))
- [x] Define the `Update-files` command and perform the initial refresh of all
  workspace files (protocol:
  [protocols/update_files.md](../protocols/update_files.md)) — 23:01:54 +06:00.
- [x] Define session-scoped auto-update (no background timer) — 23:09:35
  +06:00. See [protocols/auto_update.md](../protocols/auto_update.md).
- [x] Fix the two audit findings — 2026-11-20 10:26:13 +06:00:
  `.gitignore` exception for `work_history/auto_update.log`, and Antigravity's
  relative profile link. Contribution recorded in the worklog and changelog.
- [x] Git remote — completed by Antigravity on 2026-11-20 (origin:
  `arnob-54/Workspace`, branch `main`).
- [ ] Smoke-test the message/task conventions (add a test message to
  `agents/messages/`, then archive it).
- [ ] Verify the `Update-files` trigger when Arnob next issues the command.
