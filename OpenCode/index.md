# Index — OpenCode

Master index of the agentic workspace.
**Last updated:** 2026-11-19 23:09:35 +06:00 (Asia/Dhaka) — session auto-update added.

## Pointers

- Agent roster & communication: [agents/registry.md](agents/registry.md)
- User data: [memory/user_profile.md](memory/user_profile.md)
- Protocols & conventions:
  [protocols/agent_communication.md](protocols/agent_communication.md)
- Command protocol: [protocols/update_files.md](protocols/update_files.md)
- Session auto-update: [protocols/auto_update.md](protocols/auto_update.md)
- Active plan: [plans/centralized_agentic_system.md](plans/centralized_agentic_system.md)
- Sessions: [sessions/index.md](sessions/index.md)
- Work history: [work_history/worklog.md](work_history/worklog.md),
  [work_history/auto_update.log](work_history/auto_update.log)
- Todos: [todos/index.md](todos/index.md)

## Today — 2026-11-19

- Designed the centralized agentic system: common folder `~/Public/Agents`
  (synced with GitHub/GitLab as a repo) and this agent's workspace
  `~/Public/Agents/OpenCode` with memory, sessions, plans, protocols, todos and
  work history. See
  [plans/centralized_agentic_system.md](plans/centralized_agentic_system.md).
- 23:01:54 +06:00 — Arnob defined the `Update-files` command. Protocol written
  to [protocols/update_files.md](protocols/update_files.md); all workspace
  files updated with timestamps and details in the initial run.
- 23:09:35 +06:00 — Arnob chose a session-scoped auto-update instead of a
  timer: files refresh at checkpoints while we're actively working; nothing
  runs in the background. See
  [protocols/auto_update.md](protocols/auto_update.md).
